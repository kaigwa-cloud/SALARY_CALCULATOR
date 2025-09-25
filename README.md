def salary_calculator(payroll_no, name, gender, department,basic_salary,gross_pay, allowances, NHIF, NSSF):
    payroll_no = input("Enter your payroll number: ", payroll_no)
    name = print("Enter your name: ", name)
    gender = print("Enter your gender", gender)
    department = print("Enter your department: ", department)
    basic_salary = input("Enter your basic salary: ", basic_salary)
    try:
        basic_salary = float(basic_salary)
    except ValueError:
        print("invalid input")

    allowances = 6500 + 5500
    gross_pay = basic_salary + allowances
    NHIF = 0.02 * gross_pay
    NSSF = 0.03 * gross_pay
    gross_pay = basic_salary + allowances- NHIF - NSSF
    return basic_salary, allowances, gross_pay, NHIF, NSSF  
salary_calculator()

def paye_deduction(basic_salary, gross_pay):
    #basic_salary = int(input("Enter your basic salary: ", basic_salary)
    if basic_salary < 49000:
        return basic_salary - 0.06 * gross_pay
    elif 31000 <= basic_salary <= 39000:
        return basic_salary - 0.05 * gross_pay
    elif 19000 <= basic_salary <= 30000:
        return basic_salary - 0.04 * gross_pay
    else:
        print("Tax Exempted")
        return 0
paye_deduction()

def main():
    basic_salary,allowances, gross_pay, NHIF, NSSF = salary_calculator()
    paye_deduction = paye_deduction(basic_salary, gross_pay)
    net_salary = gross_pay - paye_deduction
    print("Your net salary is: \n, {net_salary:.2f}")
main()
