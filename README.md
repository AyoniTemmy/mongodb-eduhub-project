# mongodb-eduhub-project
A comprehensive MongoDB backend for EduHub, covering data operations, aggregations, and optimizations for an e-learning environment.

### Prerequisites

- Python 3.x
- MongoDB installed and running
- [MongoDB Compass (optional)](https://www.mongodb.com/products/compass) for GUI visualization
- Jupyter Notebook or VS Code
- `pymongo` package

# Project Structure
mongodb-eduhub-project/
├── notebooks/
│ └── eduhub_mongodb_project.ipynb
├── src/
│ └── eduhub_queries.py
├── data/
│ ├── sample_data.json
│ └── schema_validation.json
├── docs/
│ ├── performance_analysis.md
│ └── presentation.pptx
├── test_results.md
├── README.md
└── .gitignore

**
Collections & Schema Summary**
1. users
userId (string, required, unique), email (string, required, validated), role (enum: 'student' | 'instructor'), isActive (boolean), dateJoined (date)

2. courses
courseId, title, description, instructorId, category, level, price, duration, isPublished
(Foreign key: instructorId → users.userId)

4. enrollments
enrollmentId, studentId, courseId, status
Foreign keys: studentId, courseId

4. lessons
lessonId, courseId, title, content, resources

5. assignments
assignmentId, lessonId, dueDate

6. submissions
submissionId, studentId, assignmentId, grade
**Schema validation was implemented using $jsonSchema for selected collections.**

**Key Queries & Operations**
* CRUD Operations (Create, delete and update)
* Advanced Queries (join, lookup and match)
* Aggregation Pipelines

**Conclusion**
This project demonstrates the practical use of MongoDB and PyMongo in building a scalable backend for e-learning platforms. It showcases real-world database design, robust query implementations, aggregation pipelines, and performance optimization techniques.
