To create an executable JAR using the Maven build option in IntelliJ IDEA, you configure the pom.xml and then run the Maven package build. This is the most common industry method using Apache Maven.

1️⃣ Ensure Your Java Class Has a Main Method

Example:

public class HelloWorld {

    public static void main(String[] args) {
        System.out.println("Running from Maven Executable JAR");
    }

}
2️⃣ Configure pom.xml

Add the Maven Jar Plugin inside your pom.xml.

<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-jar-plugin</artifactId>
            <version>3.3.0</version>

            <configuration>
                <archive>
                    <manifest>
                        <mainClass>com.example.HelloWorld</mainClass>
                    </manifest>
                </archive>
            </configuration>

        </plugin>
    </plugins>
</build>

⚠️ Replace:

com.example.HelloWorld

with your actual package + class name.

Example:

com.learnJava.MainClass
3️⃣ Run Maven Build in IntelliJ

In IntelliJ IDEA:

Open Maven panel (right side)

Expand:

Lifecycle

Double-click:

package

This runs the Maven command:

mvn clean package
4️⃣ JAR File Location

After build completes, Maven creates the JAR in:

target/

Example:

target/myproject-1.0-SNAPSHOT.jar
5️⃣ Run the Executable JAR

Open terminal in the target folder:

java -jar myproject-1.0-SNAPSHOT.jar

Output:

Running from Maven Executable JAR
6️⃣ Maven Build Lifecycle (Important for Interviews)

When you run package in Apache Maven, it executes these phases:

validate
compile
test
package

During package, Maven creates the JAR file.

7️⃣ Typical Maven Project Structure
project-name
 ├ src
 │  ├ main
 │  │  └ java
 │  └ test
 │     └ java
 ├ pom.xml
 └ target
     └ project.jar

✅ Interview Answer

If asked:

How do you create an executable JAR using Maven in IntelliJ?

You can answer:

"We configure the maven-jar-plugin in pom.xml to define the main class and then run the Maven package lifecycle phase
    from IntelliJ, which generates the executable JAR inside the target folder."