---
title: "런타임에 바인딩 오버 로드 확인에 적용할 수 없습니다 &#39; &lt;procedurename&gt;&#39; 액세스 인스턴스가 인터페이스 형식 이므로"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb7f8a9f6eadfc9fd856ea57d362b43d25ff81a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a>런타임에 바인딩 오버 로드 확인에 적용할 수 없습니다 &#39; &lt;procedurename&gt;&#39; 액세스 인스턴스가 인터페이스 형식 이므로
컴파일러는 오버 로드 된 속성 또는 프로시저에 대 한 참조를 확인 하려고 합니다. 하지만 참조가 인수 형식 이므로 실패 `Object` 참조 하는 개체 인터페이스는 데이터 형식을 갖습니다. `Object` 인수를 사용 하면 컴파일러 바인딩이라고 참조를 확인할 수 있습니다.  
  
 이러한 경우에는 컴파일러 구현 하는 클래스 대신 기본 인터페이스를 통해 통해 오버 로드를 확인합니다. 클래스는 오버 로드 된 버전 중 하나를 이름을 바꾸거나, 컴파일러가 이름과 다르기 때문에 오버 로드 되도록 해당 버전을 고려 하지 않습니다. 이 다시 컴파일러가 참조를 해결 하려면 올바른 선택 되었을 때 이름이 변경 된 버전을 무시 합니다.  
  
 **오류 ID:** BC30933  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   사용 하 여 `CType` 에서 인수를 캐스팅 `Object` 호출 하려는 오버 로드의 시그니처에 의해 지정 된 형식과 합니다.  
  
     참고는 기본 인터페이스를 참조 하는 개체를 캐스팅 하는 데 도움이 되지는 않습니다. 이 오류를 방지 하려면 인수를 캐스팅 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 오버 로드 된에 대 한 호출 `Sub` 프로시저 컴파일 타임에이 오류가 발생 합니다.  
  
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
  
 위의 예제에서는 컴파일러에 대 한 호출을 허용 하는 경우에 `s1` 확인이 클래스를 통해 작성 된 대로 수행 `c1` 인터페이스 대신 `i1`합니다. 이 컴파일러 고려 하지 않습니다 구성이 `s2` 이름에서 다르기 때문에 `c1`에 정의 된 대로 올바른 선택은 경우에 `i1`합니다.  
  
 코드의 다음 줄 중 하나에 대 한 호출을 변경 하 여 오류를 해결할 수 있습니다.  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 코드의 이전 줄의 각 명시적 캐스팅는 `Object` 변수 `o1` 오버 로드에 대해 정의 된 매개 변수 형식 중 하나에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저 오버로딩](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [오버로드 확인](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)
