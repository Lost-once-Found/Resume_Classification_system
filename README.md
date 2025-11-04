# Resume_Classification_system
An end-to-end Resume Classification and Management Web App built using Flask, MySQL, and Machine Learning.
The system automatically downloads resumes from designated email inboxes, converts .docx files to .pdf, classifies them as resume or non-resume, and organizes them into role-based folders.
A clean web dashboard allows admins to review, shortlist, or archive resumes interactively.

Features:
->> Automated Email Resume Download
- Connects to Gmail using IMAP.
- Downloads only new/unprocessed attachments based on the last download timestamp.
- Maintains a scan history log.
  
->> Smart Resume Classification
- Classifies attachments using a trained ML model.
- Automatically skips non-resume files.
- Converts .docx to .pdf before classification.

->>Role-Based Folder Management
- Stores resumes from official emails in role-specific directories (e.g., official/ceo/resumes).
- Flexible dictionary mapping for new official roles.

->>Flask Web Dashboard
- General and Official resume lists with “YES/NO” actions.
- YES → opens candidate form, saves to DB under Interested.
- NO → options for Trash or Future Reference.
- Dynamic pages for interested_general.html, interested_official.html, trash.html, and future_reference.html.

->>Database Integration (MySQL)
- Stores candidate details, statuses, and folder tracking.
- Supports edit/delete/update operations in dashboard.

->>Auto-Runs Every 5 Hours
- Uses scheduled task to process new emails and update classification folders automatically.
  
Tech used:
    Component	                                  Technology
Backend	                    -          Flask (Python)
Frontend	                  -          HTML, CSS, JavaScript
Database	                  -          MySQL (via XAMPP)
ML Model	                  -          Scikit-learn / Custom Resume Classifier
Email Integration	          -          IMAP (Gmail API)
Automation	                -          Timestamp-based scanning, 5-hour schedule
File Conversion	            -          python-docx → PDF via reportlab


Project structure:
>>RESUME/
>Model Data/
       model.pkl
       resume_classifier_model.keras
       resume_tokenizer.pkl
       vectorizer.pkl
       
>Resume Classifier/
      app.py
      database_schema.sql
      >templates/
         future_reference.html
         general.html
         index.html
         interested_general.html
         interested_official.html
         login.html
         official.html
         trash.html
     >Training data/
        resumes/
        non_resumes/
>RESUME CODE/
        Classifier.ipynb
        downloaded_hashes.pkl
        Extractor.ipynb
        Model 2 Code.ipynb
        Model Code.ipynb
        official_resumes.json
        resume_classifier.keras
        resume_classifier_model.keras
        resume_experience_classifier.keras
        resume_tokenizer.pkl
        resume_vectorizer.pkl
        text_classifier_multiclass.keras
        text_vectorizer.pkl


