# TO-DO-LIST---JAVA
A simple and efficient console-based To-Do List application built using Java. This project allows users to manage their daily tasks by adding, viewing, completing, and deleting tasks.
📋 To-Do List Manager (Java)

A simple and efficient console-based To-Do List application built using Java. This project helps users manage daily tasks by adding, viewing, completing, and deleting them through a menu-driven interface.

🚀 Features
➕ Add new tasks
📄 View all tasks
✔ Mark tasks as completed
🗑 Delete tasks
🔁 Interactive menu system
🛠️ Technologies Used
Java
Object-Oriented Programming (OOP)
ArrayList
Scanner
📂 Project Structure
Main.java
▶️ How to Run
Clone the repository:
git clone https://github.com/your-username/todo-list-java.git
Navigate to the folder:
cd todo-list-java
Compile:
javac Main.java
Run:
java Main
💻 Full Source Code
import java.util.ArrayList;
import java.util.Scanner;

class Task {
    String description;
    boolean isCompleted;

    Task(String description) {
        this.description = description;
        this.isCompleted = false;
    }

    void markCompleted() {
        isCompleted = true;
    }

    public String toString() {
        return (isCompleted ? "[✔] " : "[ ] ") + description;
    }
}

public class Main {

    public static void main(String[] args) {
        ArrayList<Task> tasks = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("\n===== TO-DO LIST =====");
            System.out.println("1. Add Task");
            System.out.println("2. View Tasks");
            System.out.println("3. Mark Task as Completed");
            System.out.println("4. Delete Task");
            System.out.println("5. Exit");
            System.out.print("Choose option: ");

            int choice = scanner.nextInt();
            scanner.nextLine(); // clear buffer

            switch (choice) {

                case 1:
                    System.out.print("Enter task: ");
                    String desc = scanner.nextLine();
                    tasks.add(new Task(desc));
                    System.out.println("✅ Task added!");
                    break;

                case 2:
                    if (tasks.isEmpty()) {
                        System.out.println("No tasks available.");
                    } else {
                        System.out.println("\nYour Tasks:");
                        for (int i = 0; i < tasks.size(); i++) {
                            System.out.println((i + 1) + ". " + tasks.get(i));
                        }
                    }
                    break;

                case 3:
                    System.out.print("Enter task number to mark complete: ");
                    int completeIndex = scanner.nextInt() - 1;

                    if (completeIndex >= 0 && completeIndex < tasks.size()) {
                        tasks.get(completeIndex).markCompleted();
                        System.out.println("✔ Task marked as completed!");
                    } else {
                        System.out.println("❌ Invalid task number.");
                    }
                    break;

                case 4:
                    System.out.print("Enter task number to delete: ");
                    int deleteIndex = scanner.nextInt() - 1;

                    if (deleteIndex >= 0 && deleteIndex < tasks.size()) {
                        tasks.remove(deleteIndex);
                        System.out.println("🗑 Task deleted!");
                    } else {
                        System.out.println("❌ Invalid task number.");
                    }
                    break;

                case 5:
                    System.out.println("Goodbye!");
                    return;

                default:
                    System.out.println("❌ Invalid choice.");
            }
        }
    }
}
<img width="1676" height="747" alt="1" src="https://github.com/user-attachments/assets/37ec8b99-c954-4402-8e52-d66f532ee85f" />
<img width="1570" height="753" alt="2" src="https://github.com/user-attachments/assets/a523a3e9-f1f0-437c-acbb-959d02d8d3d2" />
<img width="1545" height="741" alt="3" src="https://github.com/user-attachments/assets/46040b32-80ae-48af-a757-d2235928a37f" />
<img width="1552" height="748" alt="4" src="https://github.com/user-attachments/assets/4d42e3e3-8c44-46e9-a545-fc0ae8c9247f" />

🧪 Sample Output
===== TO-DO LIST =====
1. Add Task
2. View Tasks
3. Mark Task as Completed
4. Delete Task
5. Exit
Choose option: 1

Enter task: Complete Java project
✅ Task added!
💡 Future Improvements
💾 Save tasks to file (persistent storage)
📅 Add due dates
🔥 Add priority levels
🎨 GUI using JavaFX
🤝 Contributing

Feel free to fork this repository and contribute!

📜 License

This project is open-source and available under the MIT License.
