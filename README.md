Creating a new Apache Maven project in GitHub usually involves two steps:
1️⃣ Create the Maven project locally
2️⃣ Push it to a GitHub repository

Below is the step-by-step process (commonly used with IntelliJ IDEA or any IDE).

1️⃣ Create a Maven Project
Using IntelliJ IDEA

Open IntelliJ IDEA

Click File → New → Project

Select Maven

Check Create from Archetype (optional but recommended)

Choose archetype:

org.apache.maven.archetypes:maven-archetype-quickstart

Click Next

Fill the project details:

Field	Example
GroupId	com.example
ArtifactId	demo-project
Version	1.0-SNAPSHOT

Click Finish.

Now IntelliJ will create a project like this:

demo-project
 ┣ src
 ┃ ┣ main
 ┃ ┃ ┗ java
 ┃ ┗ test
 ┃   ┗ java
 ┣ pom.xml

pom.xml is the main configuration file in Maven.

2️⃣ Initialize Git in the Project

Open terminal inside project folder and run:

git init

Add files:

git add .

Commit files:

git commit -m "Initial Maven Project"
3️⃣ Create Repository in GitHub

Open GitHub

Click New Repository

Enter repository name

Example:

demo-maven-project

Click Create Repository

4️⃣ Connect Local Project to GitHub

Copy the repository URL and run:

git remote add origin https://github.com/username/demo-maven-project.git

Push the code:

git branch -M main
git push -u origin main

Now your Maven project is uploaded to GitHub 🎉

5️⃣ Final Project Structure in GitHub
demo-maven-project
 ┣ src/main/java
 ┣ src/test/java
 ┣ pom.xml
 ┗ README.md

✅ Real-time industry workflow

Developers usually connect Apache Maven + GitHub + Jenkins so that when code is pushed to GitHub, Jenkins automatically builds the Maven project.
