import java.util.Scanner;

public class CreditPractical {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Доход (руб/мес): ");
        double income = sc.nextDouble();
        System.out.print("Ежемесячные расходы (руб/мес): ");
        double expenses = sc.nextDouble();
        System.out.print("Сумма кредита (руб): ");
        double loanAmount = sc.nextDouble();
        System.out.print("Срок (в месяцах): ");
        int termMonths = sc.nextInt();

        if (termMonths <= 0) {
            System.out.println("Неверный срок.");
            sc.close();
            return;
        }

        double monthlyPayment = loanAmount / termMonths; // простая модель без процентов
        double freeIncome = income - expenses;

        if (freeIncome <= 0) {
            System.out.println("Кредит не одобрен — нет свободного дохода.");
        } else if (monthlyPayment <= 0.5 * freeIncome) {
            System.out.println("Кредит одобрен");
        } else {
            System.out.println("Кредит не одобрен");
        }

        System.out.printf("Ежемесячный платёж: %.2f, Свободный доход: %.2f%n", monthlyPayment, freeIncome);
        sc.close();
    }
}

# fdsds
