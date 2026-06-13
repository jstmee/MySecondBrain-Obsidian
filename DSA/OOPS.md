Src pdf https://docs.google.com/document/d/1FFI3u55MnsS6WHroBwxJi2dFNP9_Kc9CtH0WiNC8DLM/edit?tab=t.0


TARGET DECK: DSA::OOPS



Q: what is oops
A: oops models a program as objects that bundle data fields with behaviour that acts on it method.
Basically it is programming in which we model things as in form of objects and classes and related it with real world example which comprises of bundling the class in form of data fields , there behaviours which acts in form of method. it related to real world object and behaviour.
<!--ID: 1781281625961-->


Q: what is class and object.
A: class is a blueprint(written once) an object(instance made many) is one built instance of that blueprint.
<!--ID: 1781281625968-->


Q: pillars of oops
A: encapsulation ( wrap data + method, restrict access using private + getters)
abstraction (hiding complexity show only essentials part interface/abstract)
inheritance (child acquires parent fields + method is- extends)
polymorphism (one name , many forms overloading+ overriding)
<!--ID: 1781281625971-->



Q: what is encapsulation
A: bundle + protect bundling things into a single unit
wrap data and the methods into single unit , and helps in control access make field private, expose getters and setters. it stops outside code from putting the object in a bad state
example medicine ka capsule dawai andar band, tum seedha powder ko haath nhi lagate, capsule ke through hi lete ho. galat does se bach gye.
<!--ID: 1781281625976-->


Q: what is abstraction
A: hide complexity and show essential parts
expose only what caller needs and hide how it works. ex cars steering and pedars are interface, the engine internals are hidden. it is achieved with abstract classes and interfaces.
matlb car chalana you only use steering and brake not how it works or engine ke andar kya ho rha hai. only imp things complexity chuppi hai.
<!--ID: 1781281625979-->


Q: difference btw encapsulation and abstraction
A: encapsulation is how u bundle and protect data implementation level, done with private getters and setters.
Abstraction is about what you expose and hide at design level, done with abstract classes and interfaces.
Encapsulation hides data, abstraction hides complexity.
<!--ID: 1781281625982-->

Q: inheritance what is it
A: A child class derives fields and methods from a parent and can add or change behaviour
ex dog is animal so dog resues animal code it models an is a relationship
example parent  child.
<!--ID: 1781283561335-->


Q: what is polymorphism
A: same method name but they behave differently depending on the object or arguments.
types compile time overloading and runtime overriding
for example one word means different meaning according to different objects,
cut bolo barbar ko baal katna, doctor ke liye operation. same naam, alg kaam. actually object decide karta hai kounsa chalega version.
<!--ID: 1781283561339-->


Q: constructor, this, super, destructors
A: constructor means woh phla din hai jab object banta hai, name, age sb create ho jata hai this matlb mai kud, aur super matlb mere papa parent class. super() se parent ke constructor chal jata hai.
constructor a special method that runs when an object is created, to initialise its fields. same same as class no return type.
defulat vs paramerterised the compiler gives no arg if you dont write, add your own to take values.
this refers to the current object, use it to tell a field apart from a parameter of the same name.
super refers to the parent, super() calls the parent constructor, super.method() calls the parents method.
constructor chaining this(args) calls another constructor in the same class must be the first line, so you write the init logic once.
Destructor/cleanup c++ has destructors that run when an object dies. java has no destructors the garbage collector frees memory, and you use try with resources or close( ) for resources.
c++ has destructor (~classname) and you often mange memory by hand new/delete. java leaves memory to garbage collector, so there is no destructors need.
<!--ID: 1781285660836-->




Q: inheritance types??
A: single one chile, one parent(b extend a)
multilevel. a chain(c extend, b extend a)
hierarchical many children of same parent dog cat extend animal
multiple one child many parent(java does not have this you simulate it by implementing multiple interfaces. c++ allow directly).
hybrid mix of all above.
![[Pasted image 20260612224801.png]]
<!--ID: 1781285260157-->


Q: what is diamond problem
A: if a class D inherit from B and C , both B and C inherit from A , then D could get two copies of A's members- which one wins? that ambiguity is the diamond problem c++ solve it with virtual inheritance so only one shares A exists.
![[Pasted image 20260612225001.png]]
java sidesteps it by banning multiple class inheritance, if two interfaces give the same default method, the class must override it to resolve the clash and can call interface.super.method()
C++ differs. it allows multiple class inheritance, so the diamond problem is real, you fix it with virtual inheritance, java forbids multiple inheritance entirely, so the diamond only appears with conflicting interface default methods.
diamond problem matlb do raaste hai dada tak jaate hai, ab pota confuse hai ki dada ki property kaunse raaste se le. Java bolta hia do baap allowed nhi hai aur c++ bolta hia ek he dada mano using virtual inheritance.
<!--ID: 1781285260162-->




Q: final keyword that block change
A: final class cannot be subclassed.
final method cannot be overriden, even in a non final class
final variable, assigned once and cannot be change again constant
final matlb ab change nhi hoga, final class matlb koi inherit nhi kar sakta, final method ko override nhi kar sakta , final variable matlb value change nhi ho sakti
<!--ID: 1781285889577-->



Q: Overloading compile time static.
A: Two methods with same name two completely different mechanism
same method name, different parameter list number, types or order, in the same class. the compiler picks which one to call from the argument types no inheritance is needed.
It is resolve at compile type why because compile check which one to call.
<!--ID: 1781288542077-->





Q: overriding run time dynamic polymorphism related to inheritance
A: a subclass redefines a parents instance method with the same signature. The jvm picks version based on actual object at run time
IN JAVA every instance method is virtual by default, so overriding just works. In C++ THE PARENT method must be marked virtual or the call binds statically to reference type and you do not get runtime dispatch.
Aha- overlaoding compile time pe decide hota hai same naam, alg argument jaise ek hi dikaan pe alag size ke kapde. overriding runtime pe child class parent ka method badal deti hai, aur jo actual object hai uska version chalta hai.
you may narrow the return type to a subtype return parent  return animal , child may return dog. and yo may widen the access modifiers protected to public but never narrow it. this is all for the child classes.
<!--ID: 1781288542098-->





Q: dynamic dispatch the vtable virtual method table
A: how does the runtime know which overriden method to call? it is through dynamic dispatch, commonly implemented with a virtual method table. the jv, spec does not literally mandate a vtable, but in practice almost every jvm c++ compiler usesa vtable dispach table each class with overridable method has a table of pointers to its actual method versions. every object holds a hidden pointer to its class vtable, so a call looks up the real method at runtime. That lookup us dynamic dispatch.
![[Pasted image 20260612234917.png]]
C++ builds a vtable only for classes that have at least one virtual method. java builds dispatch in for all non final. non static methods automatically.
Vtable matlb har class ki ek phone directory jismein likha hai kaunsa method actually kahan hai. object ke pass us directory ka number hota hai, toh call karte waqt shi version doondh leta hai yhi runtime pe sahi method chunna hai.
<!--ID: 1781288542103-->



Q: upcasting vs downcasting casting between parent and child reference.
A: Upcasting child to parent reference is always safe and is what enables runtime polymorphism. 
dOWNcasting parent to child reference is risky and can throw classcast exception so guard it with instanceof first.
animal a =new dog();  // upcast - always safe.
if(a instance of dog){   //check before downcast
     dog d=(dog) a;   // safe downcast
}
upcast matlb dog ko animal boldena kyuki dog to animal hai he, downcast matlb animal ko wapas dog banana, risky,phele instance of se check karo warna exception.
<!--ID: 1781289017910-->




Q: abstract class vs interface
A: both let u define a constract that subclasses must fullfull, but they are not interchangeable
abstract class can have  both abstract method(method with no implementations) and normal methods with data variables. It is used when multiple derived class shared common methods or data
```c++
class Animal {  
public:  
	virtual void sound() = 0; // abstract method 
	void sleep() {  
		cout << "Sleeping\n";  
	}  
};
// and a derived class must implement all pure virutal functions
class Dog : public Animal {
public:
    void sound() override {
        cout << "Bark\n";
    }
};
```
in c++ interface is usually implemented using a class having only pure virtual method use ony when you want any class inheriting this must implement it.
- Every vehicle has a speed variable and a common method → Abstract Class.
- Some objects can fly → Interface.
```c++
class Vehicle {
protected:
    int speed;
};
class Flyable {
public:
    virtual void fly() = 0;
};
class Airplane : public Vehicle, public Flyable {
public:
    void fly() override {
        cout << "Flying\n";
    }
};
```
![[Pasted image 20260613023227.png]]
In **Java/C#**, `interface` and `abstract class`  are distinct keywords. abstract means normal
In **C++**, the `interface` keyword does not exist. To make an interface in C++, you simply create an abstract class where **every single method** is a pure virtual function (written as `= 0`). Since C++ allows you to inherit from multiple classes, this achieves the exact same result.
abstract class matlb aadhi bani hui cheez jo related classes apna ke poori karti hai ek he parivaar. interface matlb ek capability ka contract jo koi bhi class utha sakti hai jaise drivable ko car bhi implement kare aur tractor bhi bale dono ka koi rhista na ho.
<!--ID: 1781290060172-->




Q: access modifiers
A: java has four levels it add a package level. C++ has no package idea at all. same keyword different rules.
c++ has no package- private level leave the keyword off and a class members are private, a struct are public.
c++ protected means this class plus derived classes only can access it
java protected is wider same package or a subclasses.
Acess modifier matlb ghar ke darwaze private apna bedroom sirf tum. protected parivaar + bachee subclasses, public main gate sab aa sakte hai, java mein ek extra darwaaza hai default package, jo poore mohalle same package ke liye khula hai, c++ main yeh mohalla wala darwaza hai he nahi.
<!--ID: 1781290868824-->




Q: static vs dynamic binding + static members
A: binding means matching a line of code that calls a method eg object.speak() to the actual code block that execute it.
Static early binding
when- happens at compile time before the program runs
how- the compiler looks at the reference type variable declared type to decide which method to call.
applies to - overload methods static methods, private method, final method because these method cannot be changed or overridden by child classes so the compiler already knows exactly knows which method to use.
Dynamic binding late 
when happens at runtime while the program is executing.
How the system looks at the actual object created in memory not the reference variable.
applies to overridden instance methods polymorphism overriding run time polymorphism
static member matlb classroom ka common blackboard ek he hai, sb students shre karte hai, kisi ek students ka apna nhi.
belong to the class- STATIC variable or method belongs to the class itself, not to individual objects. There is only one shared copy in memory. example if you have a static int object, every time you create a new object, they all update and read the exact same counter.
static method can be called without creating an object, but because it does not belong to any specific object, it cannot use regular instance field it does not know which object data to look at.
if a child class writes a static method with the exact same name and parameters as a parent static method, it is not overriding, it is called method hiding.
because static method uses static binding, the method that runs depend on reference type , not actual object. if normal method then it is overriding
```java
class Parent {
	public static void greet() { System.out.println("Hello from Parent"); }
}
class Child extends Parent {
	public static void greet() { System.out.println("Hello from Child"); } // Hides Parent's method
}
// Inside main:
Parent p = new Child(); 
p.greet(); // Prints "Hello from Parent" !!!
```
<!--ID: 1781292709384-->


Q: pass by value in java
A: in java when we pass something into a method java always makes a copy of whatever is inside the variable and hands that copy to the method. for primitive it is actual value and for object is reference java variable don't hold actual object, they hold reference memory address to where the object lives. so java copies that memory address.
<!--ID: 1781293146012-->



Q: shallow copy vs deep copy
A: shallow copy mean reference wala change and deep copy matlb phle duplicate fir diye jisse original me change na ho.
<!--ID: 1781293191723-->


