import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int T = scanner.nextInt();  // Number of test cases
        
        for (int t = 0; t < T; t++) {
            int N = scanner.nextInt();  // Size of the array
            int[] operations = new int[N];
            
            for (int i = 0; i < N; i++) {
                operations[i] = scanner.nextInt();
            }
            
            System.out.println(isValid(operations) ? "Valid" : "Invalid");
        }
        
        scanner.close();
    }
    
    public static boolean isValid(int[] operations) {
        int count = 0;
        
        for (int operation : operations) {
            if (operation == 1) {
                count++;  // Push operation
            } else if (operation == 0) {
                count--;  // Pop operation
            }
            
            if (count < 0) {
                return false;  // If pop operation exceeds push operation
            }
        }
        
        return true;
    }
}
