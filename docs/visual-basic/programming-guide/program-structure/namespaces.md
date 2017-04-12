---
title: "Visual Basic의 네임 스페이스 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.global
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names, avoiding conflicts
- naming conflicts, namespaces
- namespaces, assemblies
- Visual Basic code, namespaces
- fully qualified names
- naming conventions, naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe94e65ddbb4ebd2f7d26e8750a0a7ef5d3153af
ms.lasthandoff: 03/13/2017

---
# <a name="namespaces-in-visual-basic"></a>Visual Basic의 네임스페이스
네임스페이스는 어셈블리에 정의된 개체를 구성합니다. 어셈블리는 여러 네임스페이스를 포함할 수 있으며, 이러한 각 네임스페이스는 다른 네임스페이스를 포함할 수 있습니다. 클래스 라이브러리와 같은 대규모 개체 그룹을 사용할 때 네임스페이스는 모호성을 방지하고 참조를 단순화합니다.  
  
 예를 들어는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 정의 <xref:System.Windows.Forms.ListBox>클래스에 <xref:System.Windows.Forms?displayProperty=fullName>네임 스페이스.</xref:System.Windows.Forms?displayProperty=fullName> </xref:System.Windows.Forms.ListBox> 다음 코드 조각은 이 클래스의 정규화된 이름을 사용하여 변수를 선언하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrApplication #&6;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]  
  
## <a name="avoiding-name-collisions"></a>이름 충돌 방지  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]네임 스페이스 라고도 하는 문제를 해결 *네임 스페이스 충돌*, 클래스 라이브러리 개발자가 다른 라이브러리의 유사한 이름 사용 하 여 발생 되는에 있습니다. 기존 구성 요소와의 이러한 충돌을 *이름 충돌*이라고도 합니다.  
  
 예를 들어 `ListBox`라는 새 클래스를 만드는 경우, 프로젝트 내부에서 한정자 없이 사용할 수 있습니다. 그러나 사용 하려는 경우는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.Windows.Forms.ListBox>클래스 같은 프로젝트에 대 한 참조를 고유 하 게 정규화 된 참조를 사용 해야 합니다.</xref:System.Windows.Forms.ListBox> 참조가 고유하지 않으면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 이름이 모호하다는 오류를 표시합니다. 다음 코드 예제에서는 이러한 개체를 선언하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrApplication #&7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]  
  
 다음 그림에서는 `ListBox`라는 이름의 개체를 포함하는 두 개의 네임스페이스 계층 구조를 보여 줍니다.  
  
 ![Namespace 계층](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")  
  
 기본적으로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 만드는 모든 실행 파일에는 프로젝트와 이름이 같은 네임스페이스가 포함되어 있습니다. 예를 들어 `ListBoxProject`라는 이름의 프로젝트 내에서 개체를 정의하면 실행 파일 ListBoxProject.exe는 `ListBoxProject`라는 네임스페이스를 포함합니다.  
  
 여러 어셈블리에서 동일한 네임스페이스를 사용할 수 있습니다. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]은 이를 단일 이름 집합으로 처리합니다. 예를 들어 `Assemb1`이라는 이름의 어셈블리에서 `SomeNameSpace`라는 네임스페이스에 대한 클래스를 정의하고, `Assemb2`라는 이름의 어셈블리에서 동일한 네임스페이스에 대해 추가 클래스를 정의할 수 있습니다.  
  
## <a name="fully-qualified-names"></a>정규화된 이름  
 정규화된 이름은 개체가 정의된 네임스페이스의 이름으로 접두사가 지정된 개체 참조입니다. 클래스에 대한 참조를 만들고( **프로젝트** 메뉴에서 **참조 추가** 선택) 코드에서 개체에 대해 정규화된 이름을 사용하면 다른 프로젝트에 정의된 개체를 사용할 수 있습니다. 다음 코드 조각은 다른 프로젝트의 네임스페이스에서 개체에 대해 정규화된 이름을 사용하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrApplication #&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]  
  
 어떤 개체가 사용되고 있는지를 컴파일러가 확인할 수 있도록 해주기 때문에 정규화된 이름은 이름 충돌을 방지합니다. 그러나 이름 자체가 길고 복잡할 수 있습니다. 이를 해결하려면 `Imports` 문을 사용하여 *별칭*을 정의할 수 있습니다. 별칭이란 정규화된 이름 대신 사용할 수 있는 약식 이름을 말합니다. 예를 들어 다음 코드 예제에서는 정규화된 이름 두 개의 별칭을 만들고 이러한 별칭을 사용하여 두 개체를 정의합니다.  
  
 [!code-vb[VbVbalrApplication #&9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]  
  
 [!code-vb[VbVbalrApplication #&10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]  
  
 별칭 없이 `Imports` 문을 사용하는 경우, 한정자 없이 해당 네임스페이스의 모든 이름(프로젝트에서 고유하다면)을 사용할 수 있습니다. 같은 이름의 여러 항목을 포함하는 네임스페이스에 대한 `Imports` 문이 프로젝트에 포함된 경우, 반드시 이름을 정규화하여 사용해야 합니다. 예를 들어 프로젝트에 다음 두 개의 `Imports` 문이 포함되어 있다고 가정해 보겠습니다.  
  
 [!code-vb[VbVbalrApplication #&11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]  
  
 이름을 정규화하지 않고 `Class1`을 사용하려고 시도하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]은 `Class1` 이름이 모호하다는 오류 메시지를 표시합니다.  
  
## <a name="namespace-level-statements"></a>네임스페이스 수준 문  
 네임스페이스 내에서 모듈, 인터페이스, 클래스, 대리자, 열거형, 구조체 및 기타 네임스페이스와 같은 항목을 정의할 수 있습니다. 네임스페이스 수준에서는 속성, 프로시저, 변수 및 이벤트와 같은 항목을 정의할 수 없습니다. 이러한 항목은 모듈, 구조체 또는 클래스와 같은 컨테이너 내에서 선언되어야 합니다.  
  
## <a name="global-keyword-in-fully-qualified-names"></a>정규화된 이름의 Global 키워드  
 네임 스페이스의 중첩된 된 계층 구조를 정의한 경우 해당 계층 구조 내에서 코드에 액세스 하지 못하도록 차단 될 수 있습니다는 <xref:System?displayProperty=fullName>.NET Framework의 네임 스페이스.</xref:System?displayProperty=fullName> 다음 예제에서는 하는 계층 구조는 `SpecialSpace.System` <xref:System?displayProperty=fullName>.</xref:System?displayProperty=fullName> 네임 스페이스 블록에 액세스  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 Visual Basic 컴파일러에 대 한 참조 수 없는 성공적으로 해결 하는 결과적으로, <xref:System.Int32?displayProperty=fullName>때문에, `SpecialSpace.System` 정의 하지 않는 `Int32`.</xref:System.Int32?displayProperty=fullName> .NET Framework 클래스 라이브러리의 가장 바깥쪽 수준에서 검증 체인을 시작하려면 `Global` 키워드를 사용할 수 있습니다. 지정할 수 있습니다는 <xref:System?displayProperty=fullName>네임 스페이스 또는 클래스 라이브러리의 다른 네임 스페이스.</xref:System?displayProperty=fullName> 다음은 이에 대한 예입니다.  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 사용할 수 있습니다 `Global` 등 다른 루트 수준 네임 스페이스에 액세스 하려면 <xref:Microsoft.VisualBasic?displayProperty=fullName>, 및 프로젝트와 관련 된 모든 네임 스페이스.</xref:Microsoft.VisualBasic?displayProperty=fullName>  
  
## <a name="global-keyword-in-namespace-statements"></a>네임스페이스 문의 Global 키워드  
 사용할 수도 있습니다는 `Global` 키워드는 [Namespace 문을](../../../visual-basic/language-reference/statements/namespace-statement.md)합니다. 이렇게 하면 프로젝트의 루트 네임스페이스에서 네임스페이스를 정의할 수 있습니다.  
  
 프로젝트에서 모든 네임스페이스는 프로젝트에 대한 루트 네임스페이스를 기반으로 합니다.  Visual Studio는 프로젝트 이름을 프로젝트의 모든 코드에 대한 기본 루트 네임스페이스로 할당합니다. 예를 들어 프로젝트 이름이 `ConsoleApplication1`이면 해당 프로그래밍 요소는 해당 네임스페이스 `ConsoleApplication1`에 속합니다. `Namespace Magnetosphere`를 선언하는 경우, 프로젝트의 `Magnetosphere` 에 대한 참조는 `ConsoleApplication1.Magnetosphere`에 액세스합니다.  
  
 다음 예제에서는 `Global` 키워드를 사용하여 프로젝트에 대한 루트 네임스페이스에서 네임스페이스를 선언합니다.  
  
 [!code-vb[VbVbalrApplication #&22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]  
  
 네임스페이스 선언에서 `Global` 은 다른 네임스페이스에 중첩할 수 없습니다.  
  
 사용할 수는 [응용 프로그램 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) 보고 수정 하는 **루트 Namespace** 프로젝트의.  새 프로젝트에서 **루트 네임스페이스** 는 기본적으로 프로젝트 이름입니다. `Global` 이 최상위 네임스페이스가 되도록 하려면 **루트 네임스페이스** 항목을 지워 상자를 비울 수 있습니다. **루트 네임스페이스** 를 지우면 네임스페이스 선언에서 `Global` 키워드가 필요하지 않습니다.  
  
 `Namespace` 문이 .NET Framework에서 역시 네임스페이스인 이름을 선언하면, `Global` 키워드가 정규화된 이름으로 사용되지 않는 경우 .NET Framework 네임스페이스를 사용할 수 없게 됩니다. `Global` 키워드를 사용하지 않은 채 해당 .NET Framework 네임스페이스에 액세스하려면 `Global` 문에 `Namespace` 키워드를 포함할 수 있습니다.  
  
 다음 예제에서는 `Global` 네임스페이스 선언에 `System.Text` 키워드가 있습니다.  
  
 하는 경우는 `Global` 키워드는 네임 스페이스 선언에 없었습니다 <xref:System.Text.StringBuilder>지정 하지 않고 액세스할 수 없습니다 `Global.System.Text.StringBuilder`.</xref:System.Text.StringBuilder> `ConsoleApplication1`이라는 프로젝트에서는 `System.Text` 키워드가 사용되지 않은 경우 `ConsoleApplication1.System.Text` 에 대한 참조가 `Global` 에 액세스할 수 있습니다.  
  
 [!code-vb[VbVbalrApplication #&21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ListBox></xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms?displayProperty=fullName></xref:System.Windows.Forms?displayProperty=fullName>   
 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [방법: 명령줄을 사용 하 여 어셈블리 만들기 및 사용](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)   
 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Office 솔루션에서 코드 작성](https://msdn.microsoft.com/library/bb608596)
