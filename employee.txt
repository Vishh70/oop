class Employee {
    String empName;
    int empId;
    String address;
    String mailId;
    String mobileNo;
    double basicPay;

    public Employee(String empName, int empId, String address, String mailId, String mobileNo, double basicPay) {
        this.empName = empName;
        this.empId = empId;
        this.address = address;
        this.mailId = mailId;
        this.mobileNo = mobileNo;
        this.basicPay = basicPay;
    }

    public void display() {
        System.out.println("Employee Name: " + empName);
        System.out.println("Employee ID: " + empId);
        System.out.println("Address: " + address);
        System.out.println("Mail ID: " + mailId);
        System.out.println("Mobile No: " + mobileNo);
    }

    public void generatePaySlip() {
        double DA = 0.97 * basicPay;
        double HRA = 0.10 * basicPay;
        double PF = 0.12 * basicPay;
        double staffClubFund = 0.001 * basicPay;
        double grossSalary = basicPay + DA + HRA;
        double netSalary = grossSalary - PF - staffClubFund;

        display();
        System.out.println("Basic Pay: " + basicPay);
        System.out.println("DA: " + DA);
        System.out.println("HRA: " + HRA);
        System.out.println("PF: " + PF);
        System.out.println("Staff Club Fund: " + staffClubFund);
        System.out.println("Gross Salary: " + grossSalary);
        System.out.println("Net Salary: " + netSalary);
    }
}

class Programmer extends Employee {
    public Programmer(String empName, int empId, String address, String mailId, String mobileNo, double basicPay) {
        super(empName, empId, address, mailId, mobileNo, basicPay);
    }
}

class TeamLead extends Employee {
    public TeamLead(String empName, int empId, String address, String mailId, String mobileNo, double basicPay) {
        super(empName, empId, address, mailId, mobileNo, basicPay);
    }
}

class AssistantProjectManager extends Employee {
    public AssistantProjectManager(String empName, int empId, String address, String mailId, String mobileNo, double basicPay) {
        super(empName, empId, address, mailId, mobileNo, basicPay);
    }
}

class ProjectManager extends Employee {
    public ProjectManager(String empName, int empId, String address, String mailId, String mobileNo, double basicPay) {
        super(empName, empId, address, mailId, mobileNo, basicPay);
    }
}

public class Main {
    public static void main(String[] args) {
        Programmer programmer = new Programmer("Alice", 101, "123 Main St", "alice@example.com", "1234567890", 50000);
        TeamLead teamLead = new TeamLead("Bob", 102, "456 Elm St", "bob@example.com", "0987654321", 70000);
        AssistantProjectManager assistantPM = new AssistantProjectManager("Charlie", 103, "789 Oak St", "charlie@example.com", "1122334455", 90000);
        ProjectManager projectManager = new ProjectManager("David", 104, "321 Pine St", "david@example.com", "5566778899", 120000);

        System.out.println("Pay Slip for Programmer:");
        programmer.generatePaySlip();
        System.out.println("\nPay Slip for Team Lead:");
        teamLead.generatePaySlip();
        System.out.println("\nPay Slip for Assistant Project Manager:");
        assistantPM.generatePaySlip();
        System.out.println("\nPay Slip for Project Manager:");
        projectManager.generatePaySlip();
    }
}
