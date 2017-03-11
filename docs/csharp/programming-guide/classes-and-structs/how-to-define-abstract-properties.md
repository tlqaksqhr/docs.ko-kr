---
title: "방법: 추상 속성 정의(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "추상 속성[C#]"
  - "속성[C#], abstract"
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# 방법: 추상 속성 정의(C# 프로그래밍 가이드)
다음 예제에서는 [추상](../../../csharp/language-reference/keywords/abstract.md) 속성을 정의하는 방법을 보여 줍니다.  추상 속성 선언에서는 속성 접근자에 대한 구현을 제공하지 않습니다. 여기서는 클래스가 속성을 지원하도록 선언하지만 접근자 구현은 파생 클래스의 몫으로 남겨 둡니다.  다음 예제에서는 기본 클래스에서 상속된 추상 속성을 구현하는 방법을 보여 줍니다.  
  
 이 샘플은 파일 세 개로 구성되어 있습니다. 각 파일은 개별적으로 컴파일되고 그 결과 어셈블리는 다음 컴파일에서 참조합니다.  
  
-   abstractshape.cs: 추상 `Area` 속성이 들어 있는 `Shape` 클래스입니다.  
  
-   shapes.cs: `Shape` 클래스의 서브클래스입니다.  
  
-   shapetest.cs: `Shape` 파생 개체 일부의 영역을 표시하기 위한 테스트 프로그램입니다.  
  
 예제를 컴파일하려면 다음 명령을 사용해야 합니다.  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 이렇게 하면 실행 파일 shapetest.exe가 만들어집니다.  
  
## 예제  
 이 파일에서는 `double` 형식의 `Area` 속성을 포함하는 `Shape` 클래스를 선언합니다.  
  
 [!code-cs[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-define-abstract-p_1.cs)]  
  
-   속성에 대한 한정자는 속성 선언 자체에 배치됩니다.  예를 들면 다음과 같습니다.  
  
    ```  
    public abstract double Area  
    ```  
  
-   이 예제에서의 `Area`와 같이 추상 속성을 선언할 때 단순히 사용할 수 있는 속성 접근자를 나타내고 구현하지는 않습니다.  이 예제에서는 [get](../../../csharp/language-reference/keywords/get.md) 접근자만 사용할 수 있으므로 속성이 읽기 전용입니다.  
  
## 예제  
 다음 코드에서는 `Shape`의 서브클래스 세 개를 보여 주고 이 서브클래스에서 `Area` 속성을 재정의하여 자체 구현을 제공하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-define-abstract-p_2.cs)]  
  
## 예제  
 다음은 여러 `Shape` 파생 개체를 만들고 해당 면적을 출력하는 테스트 프로그램 코드입니다.  
  
 [!code-cs[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-define-abstract-p_3.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [방법: 명령줄을 사용하여 어셈블리 만들기 및 사용](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)