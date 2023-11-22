import java.util.*;

class Question {
    String question;
    LinkedList<String> options;
    String answer;

    Question(String question, LinkedList<String> options, String answer) {
        this.question = question;
        this.options = options;
        this.answer = answer;
    }

    boolean checkAnswer(String userAnswer) {
        return userAnswer.equalsIgnoreCase(answer);
    }
}

public class DataStructureAlgorithmQuiz {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int score = 0;
        int totalQuestions = 5;
        LinkedList<Question> questions = initializeQuestions();

        System.out.println("Welcome to the Data Structures and Algorithms Quiz!");
        System.out.println("You'll be asked " + totalQuestions + " questions. Let's begin!\n");

        long startTime = System.currentTimeMillis();
        long elapsedTime;

        for (int i = 0; i < totalQuestions; i++) {
            Question currentQuestion = questions.get(i);
            long questionStartTime = System.currentTimeMillis();
            System.out.println("Time taken: " + (System.currentTimeMillis() - startTime) / 1000 + " seconds\n");
            System.out.println("Question " + (i + 1) + ": " + currentQuestion.question);

            for (int j = 0; j < currentQuestion.options.size(); j++) {
                System.out.println((j + 1) + ". " + currentQuestion.options.get(j));
            }

            int userChoice = getUserChoice(scanner, currentQuestion.options.size());

            if (userChoice != -1) {
                String userAnswer = currentQuestion.options.get(userChoice - 1);
                if (currentQuestion.checkAnswer(userAnswer)) {
                    System.out.println("Correct!");
                    score++;
                } else {
                    System.out.println("Incorrect!");
                }
            } else {
                System.out.println("Invalid choice. Moving to the next question.");
            }

            elapsedTime = (System.currentTimeMillis() - questionStartTime) / 1000;
            System.out.println("Time taken for this question: " + elapsedTime + " seconds\n");
        }

        elapsedTime = (System.currentTimeMillis() - startTime) / 1000;
        System.out.println("Quiz ended!");
        System.out.println("Your score is: " + score + " out of " + totalQuestions);
        System.out.println("Total time taken: " + elapsedTime + " seconds");
    }

    static LinkedList<Question> initializeQuestions() {
        LinkedList<Question> questions = new LinkedList<>();
        questions.add(new Question(
                "What is the time complexity of inserting an element at the end of an array?",
                new LinkedList<>(List.of("O(1)", "O(log n)", "O(n)", "O(n^2)")),
                "O(1)"
        ));

        questions.add(new Question(
                "Which data structure uses LIFO (Last In, First Out) principle?",
                new LinkedList<>(List.of("Queue", "Heap", "Stack", "Tree")),
                "Stack"
        ));

        questions.add(new Question(
                "What sorting algorithm has the best time complexity in most cases?",
                new LinkedList<>(List.of("Bubble Sort", "Insertion Sort", "Merge Sort", "Quick Sort")),
                "Quick Sort"
        ));

        questions.add(new Question(
                "Which search algorithm works by repeatedly dividing in half?",
                new LinkedList<>(List.of("Linear Search", "Binary Search", "Depth-First Search", "Breadth-First Search")),
                "Binary Search"
        ));

        questions.add(new Question(
                "What is the data structure used in BFS (Breadth-First Search) to keep track of vertices?",
                new LinkedList<>(List.of("Stack", "Queue", "Array", "LinkedList")),
                "Queue"
        ));

        return questions;
    }

    static int getUserChoice(Scanner scanner, int optionsCount) {
        System.out.print("Enter your choice (1-" + optionsCount + "): ");
        try {
            int userChoice = Integer.parseInt(scanner.nextLine());
            if (userChoice >= 1 && userChoice <= optionsCount) {
                return userChoice;
            }
        } catch (NumberFormatException ignored) {
        }
        return -1;
    }
}
