---
title: "방법: Nullable 형식 식별(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nullable 형식[C#], 식별"
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: Nullable 형식 식별(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

C\# [typeof](../../../csharp/language-reference/keywords/typeof.md) 연산자를 사용하여 Nullable 형식을 나타내는 <xref:System.Type> 개체를 만들 수 있습니다.  
  
```  
System.Type type = typeof(int?);  
```  
  
 <xref:System.Reflection> 네임스페이스의 클래스와 메서드를 사용하여 Nullable 형식을 나타내는 <xref:System.Type> 개체를 생성할 수도 있습니다.  그러나 런타임에 <xref:System.Object.GetType%2A> 메서드나 `is` 연산자를 사용하여 Nullable 변수에서 형식 정보를 가져오려고 하면 Nullable 형식이 아니라 내부 형식을 나타내는 <xref:System.Type> 개체가 만들어집니다.  
  
 Nullable 형식의 `GetType`을 호출하면 형식이 <xref:System.Object>로 암시적으로 변환될 때 boxing 연산이 수행됩니다.  따라서 <xref:System.Object.GetType%2A>은 항상 Nullable 형식이 아니라 내부 형식을 나타내는 <xref:System.Type> 개체를 반환합니다.  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 C\# [is](../../../csharp/language-reference/keywords/is.md) 연산자도 Nullable의 내부 형식에서 작동합니다.  따라서 `is`를 사용하여 변수가 Nullable 형식인지 여부를 확인할 수 없습니다.  다음 예제에서는 `is` 연산자가 Nullable\<int\> 변수를 int로 처리하는 것을 보여 줍니다.  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## 예제  
 다음 코드를 사용하여 <xref:System.Type> 개체가 Nullable 형식을 나타내는지 여부를 확인할 수 있습니다.  이 항목의 앞부분에서 설명한 것처럼 <xref:System.Object.GetType%2A>을 호출할 때 `Type` 개체가 반환되었으면 이 코드는 항상 false를 반환합니다.  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## 참고 항목  
 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)   
 [Nullable 형식 boxing](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)