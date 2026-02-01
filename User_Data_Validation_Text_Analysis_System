user_data = [
    " Anu, anu@gmail.com , 21 ",
    "Ravi ,ravi123gmail.com, 17",
    " Suresh,suresh@gmail.com,25 ",
    "Meena,meena@gmail,22",
    ",invalid@gmail.com,30"
]

total_records = len(user_data)
valid_users = 0
invalid_users = 0
eligible_users = 0
underage_users = 0
domain_count = {}

print("---- Cleaned & Valid Records ----\n")

for record in user_data:
    record = record.strip()
    parts = record.split(",")

    
    if len(parts) != 3:
        invalid_users += 1
        continue

    name = parts[0].strip().title()
    email = parts[1].strip().lower()
    age_str = parts[2].strip()

    
    is_valid = True

    
    if name == "":
        is_valid = False

    
    if email.count("@") != 1:
        is_valid = False
    elif email.startswith("@") or email.endswith("@"):
        is_valid = False
    else:
        at_index = email.find("@")
        if "." not in email[at_index:]:
            is_valid = False

    
    if not age_str.isdigit():
        is_valid = False
    else:
        age = int(age_str)

    if not is_valid:
        invalid_users += 1
        continue

    
    valid_users += 1

    
    if age >= 18:
        eligible_users += 1
    else:
        underage_users += 1

    domain = email.split("@")[1]
    domain_count[domain] = domain_count.get(domain, 0) + 1

    
    print(f"Name: {name} | Email: {email} | Age: {age}")


print("\n---- Summary Report ----")
print("Total Records:", total_records)
print("Valid Users:", valid_users)
print("Invalid Users:", invalid_users)
print("Eligible Users (18+):", eligible_users)
print("Underage Users:", underage_users)

print("\n---- Email Domain Count ----")
for domain, count in domain_count.items():
    print(domain, ":", count)
