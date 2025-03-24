# CodeAlpha_Project_Task-Automation-with-Python-Scripts.
Project on Task Automation with Python Scripts by me...
<br>
Author-Komal Goswami
<br>
Here is code...
<br>
# Automate File Organization 

import os
import shutil
source_dir = "C:/Users/YourName/Downloads"

file_types = {
    "Images": [".png", ".jpg", ".jpeg", ".gif"],
    "Documents": [".pdf", ".docx", ".txt", ".xlsx"],
    "Videos": [".mp4", ".mkv", ".avi"],
    "Music": [".mp3", ".wav"],
}

for folder in file_types.keys():
    os.makedirs(os.path.join(source_dir, folder), exist_ok=True)

for file in os.listdir(source_dir):
    file_path = os.path.join(source_dir, file)
    if os.path.isfile(file_path):
        for folder, extensions in file_types.items():
            if file.lower().endswith(tuple(extensions)):
                shutil.move(file_path, os.path.join(source_dir, folder))
                print(f"Moved: {file} ➡ {folder}")

# Automate Data Cleaning 

import pandas as pd

df = pd.read_csv("data.csv")

df.dropna(inplace=True)

df.rename(columns={"Full Name": "Name", "Phone Number": "Phone"}, inplace=True)

df["Name"] = df["Name"].str.lower()

df.to_csv("cleaned_data.csv", index=False)

print("✅ Data cleaned successfully and saved as 'cleaned_data.csv'")

 # Automate System Maintenance

 import os
folders = [
    "C:/Windows/Temp",
    "C:/Users/YourName/AppData/Local/Temp"
]
for folder in folders:
    for file in os.listdir(folder):
        file_path = os.path.join(folder, file)
        try:
            os.remove(file_path)
            print(f"Deleted: {file_path}")
        except:
            pass

print("✅ System cleanup completed!")




