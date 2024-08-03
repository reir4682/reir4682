- 👋 Hi, I’m @reir4682
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
reir4682/reir4682 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.import random
import time

class Hamster:
    def __init__(self, name):
        self.name = name
        self.happiness = 50
        self.hunger = 50
        self.energy = 50

    def feed(self):
        print(f"{self.name} поел!")
        self.hunger -= 10
        self.happiness += 5

    def play(self):
        print(f"{self.name} играет!")
        self.happiness += 10
        self.energy -= 10

    def sleep(self):
        print(f"{self.name} спит!")
        self.energy += 20
        self.happiness -= 5

    def status(self):
        print(f"\nСтатусы хомяка {self.name}:")
        print(f"Счастье: {self.happiness}")
        print(f"Голод: {self.hunger}")
        print(f"Энергия: {self.energy}")

    def check_status(self):
        if self.happiness <= 0:
            print(f"{self.name} очень несчастен! Игра окончена.")
            return False
        if self.hunger >= 100:
            print(f"{self.name} голоден и не может больше продолжать. Игра окончена.")
            return False
        if self.energy <= 0:
            print(f"{self.name} слишком устал! Игра окончена.")
            return False
        return True

def main():
    name = input("Введите имя вашего хомяка: ")
    hamster = Hamster(name)

    while True:
        hamster.status()
        print("\nВыберите действие:")
        print("1. Покормить хомяка")
        print("2. Поиграть с хомяком")
        print("3. Уложить хомяка спать")
        print("4. Выйти из игры")

        choice = input("Ваш выбор: ")

        if choice == '1':
            hamster.feed()
        elif choice == '2':
            hamster.play()
        elif choice == '3':
            hamster.sleep()
        elif choice == '4':
            print("Спасибо за игру!")
            break
        else:
            print("Некорректный выбор. Попробуйте снова.")

        # Обновление статусов
        hamster.hunger += random.randint(5, 15)
        hamster.energy -= random.randint(5, 15)

        if not hamster.check_status():
            break
        
        time.sleep(1)

if __name__ == "__main__":
    main()
