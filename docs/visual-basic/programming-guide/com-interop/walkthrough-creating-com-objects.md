---
title: "Walkthrough: Creating COM Objects with Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "COM interop, creating COM objects"
  - "COM objects, creating"
  - "COM interop, walkthroughs"
  - "object creation, COM objects"
  - "COM objects, walkthroughs"
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Walkthrough: Creating COM Objects with Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

새 응용 프로그램이나 구성 요소를 만들 경우 .NET Framework 어셈블리를 만드는 것이 가장 좋습니다.  그러나 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 .NET Framework 구성 요소를 COM에 쉽게 노출할 수도 있습니다.  이렇게 하면 COM 구성 요소가 필요한 이전 응용 프로그램 제품군에 대한 새 구성 요소를 제공할 수 있습니다.  이 연습에서는 COM 클래스 템플릿을 사용하거나 사용하지 않고서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]을 통해 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 개체를 COM 개체로 노출하는 방법을 보여 줍니다.  
  
 COM 개체를 노출하는 가장 쉬운 방법은 COM 클래스 템플릿을 사용하는 것입니다.  COM 클래스 템플릿은 새 클래스를 만든 다음 프로젝트를 구성하여 클래스 및 상호 운용성 계층을 COM 개체로서 생성하고 운영 체제에 등록합니다.  
  
> [!NOTE]
>  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 만든 클래스를 COM 개체로 노출하여 비관리 코드에서 사용할 수도 있지만 이 개체는 진정한 COM 개체가 아니며 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 사용할 수 없습니다.  자세한 내용은 [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)을 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### COM 클래스 템플릿을 사용하여 COM 개체를 만들려면  
  
1.  **파일** 메뉴에서 **새 프로젝트**를 클릭하여 새 Windows 응용 프로그램 프로젝트를 엽니다.  
  
2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 필드에서 Windows가 선택되었는지 확인합니다.  **템플릿** 목록에서 **클래스 라이브러리**를 선택한 다음 **확인**을 클릭합니다.  새 프로젝트가 표시됩니다.  
  
3.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  **새 항목 추가** 대화 상자가 표시됩니다.  
  
4.  **템플릿** 목록에서 **COM 클래스**를 선택하고 **추가**를 클릭합니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 새 클래스를 추가하고 COM interop에 대한 새 프로젝트를 구성합니다.  
  
5.  속성, 메서드 및 이벤트와 같은 코드를 COM 클래스에 추가합니다.  
  
6.  **빌드** 메뉴에서 **ClassLibrary1 빌드**를 선택합니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 어셈블리를 빌드하고 운영 체제에 COM 개체를 등록합니다.  
  
## COM 클래스 템플릿을 사용하지 않고 COM 개체 만들기  
 COM 클래스 템플릿을 사용하지 않고 수동으로 COM 클래스를 만들 수 있습니다.  이는 명령줄에서 작업하거나 COM 개체를 정의하는 방법을 보다 자세하게 제어하려는 경우에 유용한 방법입니다.  
  
#### COM 개체를 생성하여 프로젝트를 설정하려면  
  
1.  **파일** 메뉴에서 **새 프로젝트**를 클릭하여 새 Windows 응용 프로그램 프로젝트를 엽니다.  
  
2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 필드에서 Windows가 선택되었는지 확인합니다.  **템플릿** 목록에서 **클래스 라이브러리**를 선택한 다음 **확인**을 클릭합니다.  새 프로젝트가 표시됩니다.  
  
3.  **솔루션 탐색기**에서 프로젝트를 오른쪽 마우스 단추로 클릭하고 **속성**을 클릭합니다.  **프로젝트 디자이너**가 표시됩니다.  
  
4.  **컴파일** 탭을 클릭합니다.  
  
5.  **COM Interop 등록** 확인란을 선택합니다.  
  
#### 클래스에 코드를 설정하여 COM 개체를 만들려면  
  
1.  **솔루션 탐색기**에서 **Class1.vb**를 두 번 클릭하여 해당 코드를 표시합니다.  
  
2.  클래스 이름을 `ComClass1`으로 바꿉니다.  
  
3.  다음 상수를 `ComClass1`에 추가합니다.  이러한 상수는 COM 개체가 가져야 하는 GUID\(Globally Unique Identifier\) 상수를 저장합니다.  
  
     [!CODE [VbVbalrInterop#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrInterop#2)]  
  
4.  **도구** 메뉴에서 **GUID 만들기**를 클릭합니다.  **GUID 만들기** 대화 상자에서 **레지스트리 형식**을 클릭한 다음 **복사**를 클릭합니다.  **끝내기**를 클릭합니다.  
  
5.  `ClassId`에 대한 빈 문자열을 GUID로 바꾸고 선행 및 후행 중괄호를 제거합니다.  예를 들어, Guidgen에 의해 제공된 GUID가 `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"`일 경우 코드는 다음과 같아야 합니다.  
  
     [!CODE [VbVbalrInterop#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrInterop#3)]  
  
6.  다음 예제에 나온 것처럼 `InterfaceId` 및 `EventsId` 상수에 대한 이전 단계를 반복합니다.  
  
     [!CODE [VbVbalrInterop#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrInterop#4)]  
  
    > [!NOTE]
    >  GUID가 새 것이며 고유한지 확인합니다. 그렇지 않을 경우 COM 구성 요소가 다른 COM 구성 요소와 충돌할 수 있습니다.  
  
7.  다음 예제와 같이 `ComClass` 특성을 `ComClass1`에 추가하여 클래스 ID, 인터페이스 ID 및 이벤트 ID에 대한 GUID를 지정합니다.  
  
     [!CODE [VbVbalrInterop#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrInterop#5)]  
  
8.  COM 클래스에는 매개 변수 없는 `Public Sub New()` 생성자가 있어야 합니다. 그렇지 않으면 클래스가 올바르게 등록되지 않습니다.  매개 변수 없는 생성자를 클래스에 추가합니다.  
  
     [!CODE [VbVbalrInterop#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrInterop#6)]  
  
9. 속성, 메서드 및 이벤트를 클래스에 추가하고 클래스를 `End Class` 문으로 종료합니다.  **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 어셈블리를 빌드하고 운영 체제에 COM 개체를 등록합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 생성한 COM 개체는 진정한 COM 개체가 아니기 때문에 다른 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 응용 프로그램에서 사용할 수 없습니다.  해당 COM 개체에 참조를 추가하면 오류가 발생합니다.  자세한 내용은 [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ComClassAttribute>   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md)   
 [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)