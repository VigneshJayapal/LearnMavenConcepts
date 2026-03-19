To convert a Java .class file into an executable .jar file in IntelliJ IDEA, you need to create a JAR artifact and specify the Main class (the class containing public static void main(String[] args)).

Below is the step-by-step process.

1️⃣ Ensure Your Class Has a Main Method

Example Java class:

public class HelloWorld {

    public static void main(String[] args) {
        System.out.println("Hello, Executable JAR!");
    }

}

The main() method is mandatory for an executable JAR.

2️⃣ Build the Project

Open IntelliJ IDEA

Go to Build → Build Project

This generates the .class files inside:

out/production/project-name
3️⃣ Create JAR Artifact

Go to
File → Project Structure

Select
Artifacts

Click +

Choose:

JAR → From modules with dependencies
4️⃣ Select Main Class

A window appears:

Module: Select your module

Main Class: Select the class containing main()

Example:

HelloWorld

Then click OK.

5️⃣ Build the JAR

Go to:

Build → Build Artifacts

Select:

Build

IntelliJ will generate a .jar file.

Location usually:

out/artifacts/projectname_jar/

Example:

HelloWorld.jar
6️⃣ Run the Executable JAR

Open Command Prompt / Terminal and run:

java -jar HelloWorld.jar

Output:

Hello, Executable JAR!
7️⃣ What Makes It Executable

Inside the JAR there is a MANIFEST file:

META-INF/MANIFEST.MF

Example content:

Main-Class: HelloWorld

This tells Java which class to run.

✅ Simple Flow

.java file
     ↓
compile
     ↓
.class file
     ↓
JAR artifact
     ↓
Executable JAR
