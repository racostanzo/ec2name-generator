# ec2name-generator
import random
import string

VALID_DEPARTMENTS = ["marketing", "accounting", "finops"]

def generate_ec2_names(num_instances, department_name):
    ec2_names = []
    for i in range(num_instances):
        random_chars = ''.join(random.choices(string.ascii_letters + string.digits, k=6))
        ec2_name = f"{department_name.upper()}-EC2-{random_chars}"
        ec2_names.append(ec2_name)
    return ec2_names

def main():
    num_instances = int(input("Enter the number of EC2 instances you want names for: "))
    department_name = input("Enter the name of your department (Marketing, Accounting, FinOps): ").lower()

    if department_name in VALID_DEPARTMENTS:
        ec2_names = generate_ec2_names(num_instances, department_name)
        print("\nGenerated EC2 Names:")
        for name in ec2_names:
            print(name)
    else:
        print("Invalid department. Only Marketing, Accounting, and FinOps departments are allowed to use this Name Generator.")

if __name__ == "__main__":
    main()
