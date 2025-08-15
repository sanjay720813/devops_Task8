# Task 8 - Run a Simple Java Maven Build Job in Jenkins

## 📌 Objective  
Learn how to use **Jenkins** to build a simple Java application using **Maven** — your first step into CI/CD.

---

## 🛠 Tools Required (All Free)  
- **Jenkins** (installed locally or via Docker)  
- **Java JDK** 8 or 11  
- **Maven**  
- **Git** (optional — can run from local folder)  

---

## 📦 Deliverables  
- A basic Java `HelloWorld` app (with `pom.xml`)  
- Jenkins Freestyle job configured to build it  
- Screenshot of successful build console output  

---

## 📂 Sample Dataset / Repo  
**Repo Name:** `hello-java-maven`  

**Contents:**  
```
src/main/java/HelloWorld.java
pom.xml
```

---

## 📝 Step-by-Step Guide  

### 1️⃣ Create a Java App  
```java
// HelloWorld.java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}
```

---

### 2️⃣ Create a `pom.xml` file  
```xml
<project>
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>hello</artifactId>
    <version>1.0</version>
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
```

---

### 3️⃣ Start Jenkins (if using Docker)  
```bash
docker run -p 8080:8080 jenkins/jenkins:lts
```

---

### 4️⃣ Configure Jenkins  
- Go to **Manage Jenkins → Global Tool Configuration**  
- Add **Maven** (e.g., Maven 3.8.6)  

---

### 5️⃣ Create a New Freestyle Project  
- In **Build Section**, select: **Invoke top-level Maven targets**  
- **Goals:** `clean package`  
- Save & Build the job  

---

### 6️⃣ Check Console Output  
✅ You should see: **BUILD SUCCESS**  

---

## 📸 Screenshots  

**Repository View**  
![Repository](https://github.com/sanjay720813/devops_Task8/blob/main/maven%20target.png)  

**Build Success**  
![Build Success](https://github.com/sanjay720813/devops_Task8/blob/main/build%20succes.png)  

---

**Author:** Sanjay720813  
**Repository:** [devops_Task8](https://github.com/sanjay720813/devops_Task8)
