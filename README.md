def calculate_grade(scores):
    # 1. ตรวจสอบว่าลิสต์ว่างหรือไม่ เพื่อป้องกัน ZeroDivisionError
    if not scores:
        return "No scores provided", 0

    # 2. ใช้ฟังก์ชัน sum() ของ Python เพื่อความรวดเร็วและอ่านง่าย
    total = sum(scores)
    average = total / len(scores)

    # 3. การตัดสินเกรด (Logic เดิมถูกต้องแล้ว)
    if average >= 80:
        grade = "A"
    elif average >= 70:
        grade = "B"
    elif average >= 60:
        grade = "C"
    elif average >= 50:
        grade = "D"
    else:
        grade = "F"
        
    return grade, average

# ทดสอบด้วยข้อมูลปกติ
scores = [85, 92, 78, 88, 95]
grade, avg = calculate_grade(scores)
print(f"Average: {avg}, Grade: {grade}")

# ทดสอบด้วยลิสต์ว่าง (เพื่อดูว่า Bug หายไปหรือไม่)
empty_scores = []
print(calculate_grade(empty_scores))
