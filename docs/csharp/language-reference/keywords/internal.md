---
title: "internal(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "internal_CSharpKeyword"
  - "internal"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "internal 키워드[C#]"
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# internal(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`internal` 키워드는  [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md) 형식 및 형식 멤버에 대 한.  내부 형식 또는 멤버는 다음 예제와 같이 동일한 어셈블리의 파일 내에서만 액세스할 수 있습니다.  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 액세스 한정자 `protected internal`이 있는 형식이나 멤버는 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식에서 액세스할 수 있습니다.  
  
 `internal`을 다른 액세스 한정자와 비교하려면 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) 및 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하십시오.  
  
 어셈블리에 대한 자세한 내용은 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
 내부 액세스는 구성 요소 그룹이 나머지 응용 프로그램 코드에 노출되지 않으면서 상호 작용할 수 있도록 하기 때문에 구성 요소 기반 개발에 주로 사용됩니다.  예를 들어 그래픽 사용자 인터페이스를 빌드하기 위한 프레임워크는 내부 액세스가 지정된 멤버를 사용하여 상호 작용하는 `Control` 및 `Form` 클래스를 제공할 수 있습니다.  이 멤버들은 내부 멤버이기 때문에 프레임워크를 사용하는 코드에 노출되지 않습니다.  
  
 내부 액세스 형식 또는 멤버를 해당 형식 또는 멤버가 정의된 어셈블리 외부에서 참조하면 오류가 발생합니다.  
  
## 예제  
 다음 예제에는 두 개의 파일 `Assembly1.cs` 및 `Assembly1`\_`a.cs`가 포함되어 있습니다.  첫 번째 파일에는 내부 기본 클래스 `BaseClass`가 있습니다.  두 번째 파일에서 `BaseClass`를 인스턴스화하려고 시도하면 오류가 발생합니다.  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## 예제  
 다음 예제에서는 예제 1에 사용한 것과 같은 파일을 사용하되 `BaseClass`의 액세스 수준을 `public`으로 변경합니다.  또한 `IntM` 멤버의 액세스 수준을 `internal`로 변경합니다.  이 경우 클래스를 인스턴스화할 수는 있지만 내부 멤버에 액세스할 수는 없습니다.  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)