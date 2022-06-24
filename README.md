### Hi there 👋

<!--
**kookchaerim/kookchaerim** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

<img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=Python&logoColor=white"/></a>
<img src="https://img.shields.io/badge/C-A8B9CC?style=flat&logo=C&logoColor=white"/></a>
<img src="https://img.shields.io/badge/java-007396?style=flat&logo=java&logoColor=white"> 

package game;
import java.util.Scanner;

public class Main {

   public static void main(String[] args) {
      
      Scanner sc = new Scanner(System.in);
      
      Animal avatar = null;
      
      System.out.println("---모여라 동물 친구들---");
      
      while(true) {
         
         System.out.println("--캐릭터 선택--");
         System.out.println("1.강아지");
         System.out.println("2.고양이");
         System.out.println("3.햄스터");
         
         System.out.print("입력 >> ");
         int choice = Integer.parseInt(sc.nextLine());
         
         if(choice != 1 && choice != 2 && choice != 3) {
            System.out.println("알맞은 캐릭터를 선택하세요");
            continue;
         }
         
         System.out.print("캐릭터 이름 설정");
         String name = sc.nextLine();
         
         if(choice == 1) {
            avatar = new Dog(name, 50, 50); //아바타라는 인스턴스에 도그 객체화 한 것을 넣어줌 (서로 상속관계)
            //도그타입의 인스턴스를 애니멀 타입의 인스턴스로 바꿈 업캐스팅
         }else if(choice == 2) {
            avatar = new Cat(name, 50, 50);
            
         }else if(choice == 3) {
            avatar = new Hams(name, 50, 50);
         }
         
         break;
         
      }
      
      
      while(true) {
         
         System.out.println("1. 먹이주기");
         System.out.println("2. 산책가기");
         System.out.println("3. 놀아주기");
         System.out.println("4. 종료하기");
         
         System.out.println("입력 >> ");
         int choice = Integer.parseInt(sc.nextLine());
         
         
         if(choice == 1) {
            avatar.eat();
         }else if(choice == 2) {
            avatar.walk();
         }else if(choice == 3) {
            avatar.play();
         }else if(choice == 4) {
            System.out.println("게임을 종료합니다");
            
            if(avatar instanceof Cat) {
               ((Cat)avatar).onlyCat();
            }//아바타가 캣타입이면 ...
            break;
         }else
            System.out.println("다시 입력하세요");
      }
      
   }

}

package game;

public class Hams extends Animal{

   public Hams(String name, int hp, int feed) {
      super(name, hp, feed);
      // TODO Auto-generated constructor stub
   }

   @Override
   public void walk() {
      this.hp -= 4;
      super.walk();
   }
   
   @Override
   public void eat() {
      this.hp += 4;
      super.eat();
   }
   
   @Override
   public void play() {
      System.out.println(this.name + "이랑 노는중!!");
      
      for(int i = 0; i < 10; i++) {
         
         System.out.println("찍찍");
         
         try {
            Thread.sleep(1000);
         } catch (InterruptedException e) {
            e.printStackTrace();
         }
      }
      
      System.out.println();
      super.play();
      
   }
}

package game;
import java.util.Scanner;

public class Main {

   public static void main(String[] args) {
      
      Scanner sc = new Scanner(System.in);
      
      Animal avatar = null;
      
      System.out.println("---모여라 동물 친구들---");
      
      while(true) {
         
         System.out.println("--캐릭터 선택--");
         System.out.println("1.강아지");
         System.out.println("2.고양이");
         System.out.println("3.햄스터");
         
         System.out.print("입력 >> ");
         int choice = Integer.parseInt(sc.nextLine());
         
         if(choice != 1 && choice != 2 && choice != 3) {
            System.out.println("알맞은 캐릭터를 선택하세요");
            continue;
         }
         
         System.out.print("캐릭터 이름 설정");
         String name = sc.nextLine();
         
         if(choice == 1) {
            avatar = new Dog(name, 50, 50); //아바타라는 인스턴스에 도그 객체화 한 것을 넣어줌 (서로 상속관계)
            //도그타입의 인스턴스를 애니멀 타입의 인스턴스로 바꿈 업캐스팅
         }else if(choice == 2) {
            avatar = new Cat(name, 50, 50);
            
         }else if(choice == 3) {
            avatar = new Hams(name, 50, 50);
         }
         
         break;
         
      }
      
      
      while(true) {
         
         System.out.println("1. 먹이주기");
         System.out.println("2. 산책가기");
         System.out.println("3. 놀아주기");
         System.out.println("4. 종료하기");
         
         System.out.println("입력 >> ");
         int choice = Integer.parseInt(sc.nextLine());
         
         
         if(choice == 1) {
            avatar.eat();
         }else if(choice == 2) {
            avatar.walk();
         }else if(choice == 3) {
            avatar.play();
         }else if(choice == 4) {
            System.out.println("게임을 종료합니다");
            
            if(avatar instanceof Cat) {
               ((Cat)avatar).onlyCat();
            }//아바타가 캣타입이면 ...
            break;
         }else
            System.out.println("다시 입력하세요");
      }
      
   }

}
