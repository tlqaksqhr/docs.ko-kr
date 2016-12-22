---
title: "Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30933"
  - "bc30933"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "overload resolution, with late-bound argument"
  - "BC30933"
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

컴파일러가 오버로드된 속성 또는 프로시저에 대한 참조를 확인하려고 하지만 인수가 `Object` 형식이고 참조하는 개체에 인터페이스 데이터 형식이 있으므로 참조가 실패합니다.  `Object` 인수를 사용하면 컴파일러가 참조를 런타임 바인딩으로 확인합니다.  
  
 이 경우 컴파일러는 기본 인터페이스 대신 구현 클래스를 통해 오버로드를 확인합니다.  클래스에서 오버로드된 버전 중 하나의 이름을 바꾸는 경우 컴파일러는 이름이 다르기 때문에 해당 버전을 오버로드로 간주하지 않습니다.  따라서 참조 확인을 위해 이 버전을 선택해야 하는데도 불구하고 컴파일러에서 이름이 바뀐 버전을 무시하게 됩니다.  
  
 **오류 ID:** BC30933  
  
### 이 오류를 해결하려면  
  
-   `CType`을 사용하여 인수를 `Object`에서 호출할 오버로드의 시그니처에 의해 지정된 형식으로 캐스팅합니다.  
  
     이로 인해 참조하는 개체를 기본 인터페이스로 캐스팅하는 데 도움이 되지는 않습니다.  이 오류를 방지하려면 인수를 캐스팅해야 합니다.  
  
## 예제  
 다음 예제에서는 컴파일 타임에 이 오류를 발생시키는 오버로드된 `Sub` 프로시저에 대한 호출을 보여 줍니다.  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 위 예제에서 컴파일러가 작성된 대로 `s1`에 대한 호출을 허용하는 경우 `i1` 인터페이스 대신 `c1` 클래스를 통해 확인이 수행됩니다.  즉, `i1`에 정의된 바에 따라 올바를지라도 `c1`에서 이름이 다르기 때문에 컴파일러는 `s2`를 고려하지 않습니다.  
  
 호출을 다음 코드 줄 중 하나로 변경하여 이 오류를 해결할 수 있습니다.  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 위의 각 코드 줄은 `Object` 변수 `o1`을 오버로드에 대해 정의된 매개 변수 형식 중 하나로 명시적으로 캐스팅합니다.  
  
## 참고 항목  
 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Overload Resolution](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)