# 🐾 Veterinary Clinic Database System  
A relational database project designed to support daily operations inside a veterinary clinic, including **pet management, doctor assignments, diagnoses, treatments, appointments, and branch operations**.  
This system follows **proper database design**, **entity modeling**, and **3NF normalization** to ensure consistency, integrity, and scalability.

---

## 📌 Project Overview  
Veterinary clinics manage large amounts of information — pet owners, pets, doctors, employees, diagnoses, treatments, and branches.  
This project builds a **clean, normalized relational database** that helps the clinic manage:

- 🐶 Pet medical history  
- 👨‍⚕️ Doctor information & specialties  
- 🧾 Diagnosis records  
- 💊 Medications & dosages  
- 🧍 Employees and roles  
- 🏥 Clinic branches  
- 📅 Appointment records  

The database ensures **accurate tracking**, reduces errors, and supports future system expansion.

---

## 🎯 Objectives  
The project focuses on designing and implementing a robust relational database using:

1. **Entity Identification & Modeling**  
2. **ERD Construction (Conceptual & Logical)**  
3. **Applying Normalization (1NF → 2NF → 3NF)**  
4. **Defining Business Rules & Functional Dependencies**  
5. **Creating Tables, Attributes, Primary Keys, and Relationships**

---

## 🧩 Identified Entities  

### **1. Owner**
Represents all pet owners registered in the clinic.  
**Primary Key:** `Phone_number`

| Attribute | Description |
|----------|-------------|
| Phone_number | Unique identifier of pet owner |
| Name | Owner’s name |
| Email | Owner’s email |

---

### **2. Pet**
All pets treated or tracked in the clinic.  
**Primary Key:** `Pet_ID`  
**Foreign Key:** `Phone_number` → Owner

| Attribute | Description |
|----------|-------------|
| Pet_ID | Unique pet identifier |
| Name | Pet name |
| DOB | Date of birth |
| Type | Animal type |
| Sex | Male/Female |
| Fur_color | Color |

---

### **3. Employees (Parent Entity)**
General employees working in the clinic.  
**Primary Key:** `E_ID`  
Has two child entities: **Doctor**, **Other_Employee**

| Attribute | Description |
|----------|-------------|
| E_ID | Unique identifier |
| E_name | Employee name |
| E_phone | Employee phone |
| Salary | Employee salary |
| Emp_type | Doctor / Staff |
| Branch_num | FK → Branches |

---

### **4. Doctor (Child of Employees)**
**Primary Key / FK:** `E_ID`

| Attribute | Description |
|----------|-------------|
| Specialty | Doctor’s specialization |

---

### **5. Other_Employee (Child of Employees)**
**Primary Key / FK:** `E_ID`

| Attribute | Description |
|----------|-------------|
| Position | Job role |

---

### **6. Branches**
Clinic branch information.  
**Primary Key:** `Branch_num`

| Attribute | Description |
|----------|-------------|
| Branch_num | Unique branch number |
| B_name | Branch name |
| Address | Branch address |

---

### **7. Diagnosis**
Medical diagnosis made for a pet.  
**Primary Key:** `Diagnosis_ID`  
**Foreign Keys:** `Pet_ID`, `E_ID` (doctor)

| Attribute | Description |
|----------|-------------|
| Diagnosis_ID | Unique diagnosis record |
| Illness | Detected illness |
| Treatment (name, dose) | Multivalued attribute (handled by associative table) |
| Date | Diagnosis date |

---

### **8. Medicine**
List of clinic medicines.  
**Primary Key:** `Med_num`

| Attribute | Description |
|----------|-------------|
| Med_num | Unique medicine ID |
| Name | Medicine name |
| Dose | Dose quantity |

---

## 🧠 Business Rules  

### **Owner–Pet**
- One owner can have **many** pets  
- A pet belongs to **one** owner  

### **Employees–Branches**
- Each employee works in **one branch**  
- Each branch has **many employees**

### **Employee–Doctor/Other_Employee**
- Employee is a **parent entity**  
- Employee must be **either doctor or staff (not both)**

### **Diagnosis–Doctor**
- One doctor can perform **many diagnoses**  
- Each diagnosis is made by **one doctor**

### **Diagnosis–Pet**
- One pet may have **zero or many diagnoses**  
- Each diagnosis belongs to **one pet**

---

## 🧮 Normalization Summary  

### ✔️ 1NF
- No repeating groups  
- All attributes are atomic  
- Proper primary keys assigned  

### ✔️ 2NF
- No partial dependencies  
- All non-key attributes depend on the **whole** key  

### ✔️ 3NF
- No transitive dependencies  
- All non-key attributes depend **only on the primary key**  

---

##📚 Learning Outcomes

1. Built a fully normalized relational database (3NF)

2. Identified entities, dependencies, and business rules

3. Constructed a complete ERD with parent–child relationships

4. Applied good database modeling practices

5. Understood multivalued & associative entities

6. Designed queries linking diagnoses, pets, medicines, and doctors

---

##🐾 Summary

This database system provides a clean, scalable structure for clinic operations, supporting efficient pet medical tracking, doctor management, and diagnosis recording.
It is suitable for extension into a full application, integrating UI, backend systems, or analytics dashboards.
## 🔗 Functional Dependencies  

