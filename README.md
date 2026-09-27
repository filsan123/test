# test
welcom c# oneimport java.util.Scanner;

public class DecimalToBinary {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // 1. In ka qaadno lambarka isticmaalaha
        System.out.print("Geli lambar decimal ah: ");
        int decimal = scanner.nextInt();
        
        // 2. Sida ugu fudud (Habka u diyaarsan ee Java)
        String binaryBuiltIn = Integer.toBinaryString(decimal);
        System.out.println("Binary-ga lambarka " + decimal + " waa: " + binaryBuiltIn);
        
        // 3. Habka xisaabta (Math/Logic) ka dambeeya
        System.out.println("\n--- Sida xisaab ahaan loo sameeyo ---");
        String binaryManual = convertToBinary(decimal);
        System.out.println("Natiijada (Manual): " + binaryManual);
        
        scanner.close();
    }
    
    // Function xisaabiya binary-ga marba 2 u qeybiya
    public static String convertToBinary(int n) {
        if (n == 0) return "0";
        
        StringBuilder binary = new StringBuilder();
        while (n > 0) {
            int remainder = n % 2; // Haraaga marka 2 loo qeybiyo (0 ama 1)
            binary.insert(0, remainder); // Haraaga horteeda geli
            n = n / 2; // Lambarka 2 u qeybi
        }
        return binary.toString();
    }
}
