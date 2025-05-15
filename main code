import pandas as pd
import os

# Your data structures
subject = {
    "math": {"name": "ahre sir", "lecture": 0, "date": [], 'slot': [], 'absent': []},
    "physics": {"name": "patil madam", "lecture": 0, "date": [], 'slot': [], 'absent': []},
    "chemistry": {"name": "kulkarni sir", "lecture": 0, "date": [], 'slot': [], 'absent': []},
    "fds": {"name": "dhanwate madam", "lecture": 0, "date": [], 'slot': [], 'absent': []},
    "psp": {"name": "gawali madam", "lecture": 0, "date": [], 'slot': [], 'absent': []}
}

student = {
    1: {"name": "Om", "math": 0, "physics": 0, "chemistry": 0, "fds": 0, "psp": 0},
    2: {"name": "Suraj", "math": 0, "physics": 0, "chemistry": 0, "fds": 0, "psp": 0},
    3: {"name": "Shreyash", "math": 0, "physics": 0, "chemistry": 0, "fds": 0, "psp": 0},
    4: {"name": "Manish", "math": 0, "physics": 0, "chemistry": 0, "fds": 0, "psp": 0},
    5: {"name": "Sarthak", "math": 0, "physics": 0, "chemistry": 0, "fds": 0, "psp": 0}
}
def mark_attendence():
    #global n
    #n=input("which subject attendence you want to mark = ")
    total_lecture=0
    
    while True:
        ds = input("Input the date and slot: ").split()
        date = ds[0]
        slot =ds[1]
        conflict = False
        for sub in subject:
            if date in subject[sub]["date"] and slot in subject[sub]["slot"]:
                conflict = True
                print(f"Conflict detected! The slot '{slot}' on '{date}' is already booked for '{sub}'. Please enter a different slot.")
                break  
        if not conflict:
            break  

    #d_s[dt].append(ds)
    subject[n]["lecture"]+=1
   
    #print(subject[n]["lecture"]) 
    subject[n]["date"].append(date)
    #print(subject[n]["date"])
    subject[n]["slot"].append(slot)
    #print(subject[n]["slot"])
    absent_list=list(map(int,input('Enter absnet number').split()))
    subject[n]["absent"].append(absent_list)
    #print(absent_list)
    for i in student.keys():
        if i not in absent_list:
            student[i][n]+=1

def display_subject_attendence():
    per=0    
    #ch=input("do you want to dislpay the the subjec attendence= ")
    #n=input("which subject attendence you want to mark = ")
    print("Following is the attendence of  = ",n)
    if True:#ch.lower()=='yes': 
        
        for i in student.keys():
          if student[i][n]>0:  
           per=student[i][n]/subject[n]['lecture']*100
           print(f"{student[i]['name']}--{per:.2f}")
          else:
              print(f"{student[i]['name']}--0.00")
'''def display_overall_attendence():
    #chh=input("do you want to dislpay the the Overall  attendence= ")
    total_lecture=0
    if True:#chh.lower()=='yes':
        for  sub in subject:
            total_lecture +=subject[sub]["lecture"]
           #print(f'tatal lecture ={total_lecture}')
        for i in student.keys():
            total_attended = 0
            for sub in subject:
                 if student[i][n]>0:
                    total_attended += student[i][sub]
                    overall_percentage = (total_attended / total_lecture) * 100
                    print(f"{student[i]['name']}--{overall_percentage:.2f}") 
                 else:
                    print(f"{student[i]['name']}--0.00")'''
def display_overall_attendence():
    total_lecture = 0
    for sub in subject:
        total_lecture += subject[sub]["lecture"]
    for i in student.keys():
        total_attended = 0

        for sub in subject:
            total_attended += student[i][sub]
        if total_attended > 0:
            overall_percentage = (total_attended / total_lecture) * 100
        else:
            overall_percentage = 0.00

       
        print(f"{student[i]['name']}--{overall_percentage:.2f}")
                    
def edit_attendance():
    ds = input("Input the date and slot to edit (e.g., 'YYYY-MM-DD slot_name'): ").split()
    date, slot = ds[0], ds[1]
    found = False

    for sub in subject:
        if date in subject[sub]["date"] and slot in subject[sub]["slot"]:
            found = True
            print(f"Editing attendance for '{sub}' on date '{date}' and slot '{slot}'.")
            index = subject[sub]["date"].index(date)

            for student_id in student.keys():
                if student_id not in student[sub]["absent"][index]:
                    student[student_id][sub] -= 1
            absent_list = list(map(int, input('Enter updated absent numbers: ').split()))
            
            for i in student.keys():
                student[i][sub] -= 1
                if i not in absent_list:
                    student[i][sub] += 1
            print("Attendance successfully Editted.")
            break
    
    if not found:
        print("No matching  found ")
def delete_attendance():
    print(subject)
    sub =n
    ds = input("Input the date and slot to delete (e.g., 'YYYY-MM-DD slot_name'): ").split()
    date, slot = ds[0], ds[1]
    found = False

    if sub in subject and date in subject[sub]["date"] and slot in subject[sub]["slot"]:
        found = True
        index = subject[sub]["date"].index(date)
        print(f"Deleting attendance for {sub} on {date}, slot {slot}.")

        # Update attendance details
        subject[sub]["lecture"] -= 1
        subject[sub]["date"].pop(index)
        subject[sub]["slot"].pop(index)
        absent_list = subject[sub]["absent"].pop(index)

        for student_id in student.keys():
            if student_id not in absent_list:
                student[student_id][sub] -= 1

        print("Attendance successfully deleted.")
    if not found:
        print("No matching record found for the given date and slot.")
def display_menu():
    print("\n--- Main Menu ---")
    print("1. Mark Attendance")
    print("2. Display Subject Attendance")
    print("3. Display Overall Attendance")
    print("4. Edit Attendance")
    print("5. Delete Attendance")
    print("6. Exit")
def time():
    import datetime


    now = datetime.datetime.now()
    current_date = now.strftime("%d-%m-%y")  
    current_time = now.strftime("%H:%M:%S")  
    current_day = now.strftime("%A") 
    print(f"Date: {current_date}")
    print(f"Time : {current_time}")
    print(f"Day -: {current_day}")
#include<stdio.h>
global n

n=input("enter the subject name  ")
print(f'Welcome! Dear {subject[n]["name"]}')
time()
while True:
    display_menu()
    choice = input("Enter your choice: ")
    if choice == "1":
        print("You selected 'Mark Attendance'")
        mark_attendence()
        
        
    elif choice == "2":
            print("You selected 'Display Subject Attendance'")
            display_subject_attendence()
        
    elif choice == "3":
            print("You selected 'Display Overall Attendance'")
            display_overall_attendence()
        
    elif choice == "4":
            print("You selected 'Edit Attendance'")
            edit_attendance()
        
    elif choice == "5":
            print("You selected 'Delete Attendance'")
            delete_attendance()
        
    elif choice == "6":
            print("Exiting the program. Goodbye!")
            break
    elif choice == "7":
            import pandas as pd
            df = pd.DataFrame(subject)
            print(df)   
    else:
            print("Invalid choice! Please try again.")
'''import pandas as pd
df = pd.DataFrame(subject)
path=r"D:\classroom attendence tracker\attendence.xlsx"
with pd.ExcelWriter(path) as om:
    df.to_excel(excel_writer=om, sheet_name='att')

print("Dictionary has been saved to 'output.xlsx'") '''
def export_to_excel():
    save_path = r"D:\classroom attendence tracker\attendance_report.xlsx"
    os.makedirs(os.path.dirname(save_path), exist_ok=True)
    with pd.ExcelWriter(save_path, engine='openpyxl') as writer:
        # Summary sheet 
        summary_data = []
        for sub, details in subject.items():
            summary_data.append({
                "Subject": sub.capitalize(),
                "Teacher": details["name"],
                "Total Lectures": details["lecture"],
            })
        pd.DataFrame(summary_data).to_excel(writer, sheet_name="Summary", index=False)
       
        # Updated Student Summary sheet
        student_summary = []
        total_lectures_all = sum(sub["lecture"] for sub in subject.values())
        
        for roll, info in student.items():
            # Create row with basic info
            row = {
                "Roll No": roll,
                "Name": info["name"]
            }
            
            # Add attendance for each subject
            total_attended = 0
            for sub in subject.keys():
                row[sub.capitalize()] = info[sub]
                total_attended += info[sub]
            
            # Add totals
            percentage = (total_attended / total_lectures_all * 100) if total_lectures_all > 0 else 0
            row.update({
                "Total Attended": total_attended,
                "Total lecture": total_lectures_all,
                "Percentage": f"{percentage:.2f}%"
            })
            
            student_summary.append(row)
        
        pd.DataFrame(student_summary).to_excel(writer, sheet_name="Student Summary", index=False)
        
        # Subject sheets
        for subject_name, details in subject.items():
            if not details["date"]:
                continue 
            data = []
            for roll, info in student.items():
                row = {"Roll No": roll, "Name": info["name"]}
                cumulative = 0
                
                for i, (date, slot) in enumerate(zip(details["date"], details["slot"])):
                    present = 0 if roll in details["absent"][i] else 1
                    cumulative += present
                    row[f"{date}"] = cumulative  
                
                data.append(row)
            
            df = pd.DataFrame(data)
            col_order = ["Roll No", "Name"] + details["date"]
            df[col_order].to_excel(writer, sheet_name=subject_name[:31], index=False)

    print(f"\nExcel report generated at: {save_path}")
export_to_excel()
