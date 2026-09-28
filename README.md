tasks = []

def show_tasks():
    if not tasks:
        print("Список задач пуст.")
    else:
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")

def add_task():
    task = input("Введите задачу: ")
    if task:
        tasks.append(task)
        print("Задача добавлена.")

def edit_task():
    show_tasks()
    number = int(input("Введите номер задачи: "))
    if 1 <= number <= len(tasks):
        tasks[number - 1] = input("Введите новое название: ")
        print("Задача изменена.")

def delete_task():
    show_tasks()
    number = int(input("Введите номер задачи: "))
    if 1 <= number <= len(tasks):
        tasks.pop(number - 1)
        print("Задача удалена.")

def main():
    while True:
        print("""
1. Показать задачи
2. Добавить задачу
3. Редактировать задачу
4. Удалить задачу
5. Выход
""")

        choice = input("Выберите пункт: ")

        if choice == "1":
            show_tasks()
        elif choice == "2":
            add_task()
        elif choice == "3":
            edit_task()
        elif choice == "4":
            delete_task()
        elif choice == "5":
            print("До свидания!")
            break
        else:
            print("Такого пункта нет.")

if __name__ == "__main__":
    main()
