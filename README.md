# Public Website (Hello World) - Python

This repository contains a simple Python web application that displays a "Hello World" message on a public website. The purpose of this project is to provide a basic template for creating a Python web application and deploying it on a public server.

## Prerequisites

Before getting started, ensure that you have the following prerequisites installed:

- Python (version 3.x)
- Pip (Python package installer)
- Flask (Python web framework)
- Git (version control system)

## Steps to Create the Website

Follow the steps below to create and deploy the public website:

1. **Clone the Repository**: Begin by cloning this repository to your local machine using the command: `git clone https://github.com/AleksGadGeek/pythonsretest.git`

2. **Create and Activate Virtual Environment**: Change into the project directory and create a virtual environment by running the command: `python3 -m venv env`. Activate the virtual environment using the command: `source env/bin/activate` (for macOS/Linux) or `env\Scripts\activate` (for Windows).

3. **Install Dependencies**: Install the necessary dependencies by running the command: `pip install -r requirements.txt`. This will install Flask, the web framework used in this project.

4. **Run the Application**: Run the Python application using the command: `python app.py`. The application should now be running locally on `http://localhost:5000`. You can access this URL in your web browser to see the "Hello World" message.

5. **Deploy to a Public Server**: To deploy the website on a public server, you need to choose a hosting provider (e.g., Heroku, PythonAnywhere, AWS, etc.). Follow the specific deployment instructions provided by your chosen hosting provider.

6. **Update Website Content**: Modify the `app.py` file to update the content of the website. You can customize the "Hello World" message or add additional functionality as per your requirements.

7. **Commit and Push Changes**: Once you have made the desired changes, commit and push your changes to the remote repository using the appropriate Git commands.

8. **Monitor and Maintain**: Ensure that your public website is running smoothly by monitoring its performance and addressing any issues that arise. Regularly update the codebase as required to keep the website up-to-date.

## Contributing

Contributions are welcome! If you have any suggestions, improvements, or bug fixes, please open an issue or submit a pull request.

## License

This project is licensed under the OpenSourcelicense.

---

Answers of Challenge

SRE Technical Challenge: 

1. Explain TTD, TTR and the importance of measuring it?
Measuring TTD and TTR provides valuable insights into an organization's ability to detect and respond to security incidents. By monitoring these metrics, organizations can identify areas for improvement, enhance incident response capabilities, and ensure compliance with industry regulations.


2. What are the benefits of distributed tracing?

It enhances visibility by providing a comprehensive view of request flow across various services. 
It enables root cause analysis by tracing the exact path of a request, leading to quicker problem resolution. 
Performance optimization is possible through identifying bottlenecks and optimizing resource allocation. 
Service dependencies can be mapped to aid in capacity planning and system changes. 
Distributed tracing facilitates collaboration and communication among teams. 
It enables proactive monitoring and anomaly detection, ensuring issues are addressed before they impact users. 
Lastly, it assists in scalability testing and performance analysis. 
Overall, distributed tracing improves system understanding, performance, issue resolution, and collaboration, resulting in more reliable applications.


 3. What is the purpose of postmortems? 
Postmortems, also known as incident retrospectives, serve several important purposes. They aim to understand incidents by analyzing their causes and timeline. 
Postmortems also identify lessons learned for preventing future incidents. 
They enhance communication and collaboration within teams and foster a blameless culture that focuses on learning, not blaming individuals. 
The ultimate goal is continuous improvement, achieved by iterating on incident response processes and improving system resilience. 
By conducting regular postmortems, organizations can create a culture of learning and enhance the overall reliability of their systems.

4. How do you practice blameless postmortems? 
We propose establishing weekly meetings or standups when a major incident occurs and it has caused disruptions. During these meetings, we will discuss with the team the response time, how the problem was identified, what actions were taken to correct it, and which measures or best practices were employed. We will also make note of any actions that were ineffective. It is important to remember that mistakes are opportunities for learning, and we can learn more when we identify shortcomings without assigning blame. Instead, we will foster a team approach and remain attentive to future incidents in order to learn from both the positives and negatives and rectify any mistakes that may have been made. Being on the same page and working together to solve problems is essential.


5. What is "Continuous Integration" with reference to Jenkins? 
In Jenkins, continuous integration refers to automatically building and testing code changes as they are committed to a version control system. This practice promotes collaboration, ensures that the software is always in a working state, and provides quick feedback on code quality. Jenkins helps reduce manual errors and allows developers to integrate their changes frequently, leading to faster development cycles and improved software reliability.


6. Create a public http://github.com repository with a website (hello world) based in python including a detailed http://README.md with a playbook for the steps. 

app.py

#python app Hello world
from flask import Flask
app = Flask(__name__)
@app.route('/')
def hello_world():
    return 'Hello, World!'
if __name__ == '__main__':
    app.run()


7. Include a pipeline example in your GitHub repository for Automatic Deployment with any python change. 

Here's an example of using a continuous integration/continuous deployment (CI/CD) pipeline with GitHub Actions for automatic deployment whenever there is a change in the Python code:

1. Create a new file called `.github/workflows/deploy.yml` in your repository.

2. Add the following content to `deploy.yml`:


name: Deploy

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.x'

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt

      - name: Run tests
        run: |
          python -m unittest discover -s tests

      - name: Deploy
        run: |
          # Any deployment commands or scripts go here
          # For example, you can use scp or rsync to copy the files to a server


8. Include an open-source tool to do vulnerability tests to your code.
An open source tool that you can use for vulnerability testing in your Python code, with compatibility for Jenkins integrations, is Bandit.

Bandit is a security linter that analyzes your Python code and identifies common security vulnerabilities such as potential XSS (Cross-Site Scripting) attacks, SQL injection flaws, and more.
