# Log2_Acad
# Application Design

## Frontend

### 1. SignUp/Login Page
- **Features**:
  - User can Sign Up or Login.
  - After authentication, the user is redirected to the **List of Courses** page.
  
### 2. List of Courses
- **Features**:
  - Display a list of courses available.
  - Sidebar displays a list of courses.
  - On clicking any course, it redirects to the **LearningPage**.

### 3. LearningPage
- **Features**:
  - Displays a list of syllabus, with each topic and its respective subtopics.
  - On clicking any subtopic, the user is redirected to the **LecturePage** (if authenticated).
  - **Progress Block** on the right side, showing the user’s progress in the course.

### 4. LecturePage
- **Features**:
  - Display the concept of the topic as text, along with an embedded video explaining the topic.
  - Sidebar displays the list of syllabus and subtopics.
  - A button to practice code after viewing the lecture.

### 5. CodingPage
- **Features**:
  - Problem Statement and Code Input area.
  - Output area to display test case results.
  - Language selection options for the user to choose the programming language.
  - Right side with optional videos to assist in solving the coding problem.

---

## Backend

### 1. Courses
- **Features**:
  - Stores the list of available courses.
  - Each course will have a unique identifier and relevant metadata.

### 2. List of Topics
- **Features**:
  - Each course will have a list of topics.
  - Each topic will be associated with a title and description.

### 3. SubTopics
- **Features**:
  - Each topic can have several subtopics that will be linked to lectures.
  - Each subtopic will have a title, description, and a corresponding video URL.

### 4. Content of SubTopics
- **Features**:
  - Detailed content (text-based explanation) for each subtopic.
  - Accompanying multimedia content like images or documents, if applicable.

### 5. URLs of Videos
- **Features**:
  - Each subtopic will have a link to an external video resource (YouTube, Vimeo, etc.) for further learning.

### 6. User Data
- **Features**:
  - Stores user information such as name, email, and authentication status.
  - Tracks user progress in courses, topics, and subtopics.
  - Stores coding submissions and related data.

---

## Database Design

### 1. User Info
- **Fields**:
  - `user_id` (Primary Key)
  - `name`
  - `email`
  - `password_hash`
  - `courses_progress` (List of progress for each course user has enrolled in)

### 2. Topic Details
- **Fields**:
  - `topic_id` (Primary Key)
  - `course_id` (Foreign Key to Courses table)
  - `title`
  - `description`
  - `subtopics` (List of Subtopic IDs)

### 3. URLs of Videos for Each Main Title
- **Fields**:
  - `subtopic_id` (Foreign Key to Subtopics table)
  - `video_url`
  - `video_description`

---

## Flow Overview

### Frontend Flow
1. **User Authentication** (SignUp/Login)
2. **List of Courses** (Display course list with sidebar navigation)
3. **LearningPage** (Display syllabus with topics/subtopics and progress block)
4. **LecturePage** (Concepts, videos, and sidebar)
5. **CodingPage** (Problem statements, code input, output, language selection)

### Backend Flow
1. **Courses Management** (Store and manage course data)
2. **Topic and Subtopic Management** (Store and link topics/subtopics for each course)
3. **User Data Management** (Store user info, progress, and coding submissions)

---

## Notes
- The application is designed to handle both the learning and coding aspects of a course in a seamless flow.
- The backend will ensure secure storage of user data, course details, and progress tracking.
