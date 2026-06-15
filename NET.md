

**1. Class**  
A class is a blueprint.

**2. Object**  
An object is the real thing created from the class.

Car myCar = new Car();  
myCar.Brand = "Toyota";  
myCar.Speed = 80;  
myCar.Drive();

**3. Property**  
Properties store data about the object.
public string Brand { get; set; }  
public int Speed { get; set; }

**4. Method**  
A method is what the object can do.
public void Drive()  
{  
Console.WriteLine($"{Brand} is driving");  
}


## 1) Encapsulation

Keep data and behavior together in one class, and control access.

public class BankAccount  
{  
public string Owner { get; set; }  
private decimal Balance { get; set; }  
  
public void Deposit(decimal amount)  
{  
if (amount > 0)  
Balance += amount;  
}  
  
public decimal GetBalance()  
{  
return Balance;  
}  
}

Why?  
Because you do **not** want random code doing this:
account.Balance = -999999;

So `Balance` is private.

## 2) Inheritance

One class can reuse another class.
public class Animal  
{  
public void Eat()  
{  
Console.WriteLine("Eating...");  
}  
}  
  
public class Dog : Animal  
{  
public void Bark()  
{  
Console.WriteLine("Woof!");  
}  
}

Usage:
Dog dog = new Dog();  
dog.Eat();  
dog.Bark();


## 3) Polymorphism

Same method name, different behavior.
public class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("Some sound");
    }
}

public class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Woof");
    }
}

public class Cat : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Meow");
    }
}


dotnet new console -n ProjectName
cd ProjectName
dotnet run
