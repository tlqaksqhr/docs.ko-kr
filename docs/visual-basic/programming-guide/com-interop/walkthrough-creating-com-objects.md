---
title: "연습: Visual Basic을 사용하여 COM 개체 만들기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff7d3868a2e3ddaba06ebc6f98c8eacfc7299366
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a>연습: Visual Basic을 사용하여 COM 개체 만들기
새 응용 프로그램 또는 구성 요소를 만들 때.NET Framework 어셈블리를 만드는 것이 좋습니다. 그러나 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 도 쉽게 com.NET Framework 구성 요소를 노출 하려면 이 COM 구성 요소를 필요로 하는 이전 응용 프로그램 제품군에 대 한 새 구성 요소를 제공할 수 있습니다. 이 연습에서는 사용 하는 방법을 보여 줍니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 노출 하도록 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 와 COM 클래스 템플릿을 사용 하지 않고 COM 개체로 개체입니다.  
  
 COM 클래스 템플릿을 사용 하 여 COM 개체를 노출 하는 가장 쉬운 방법은 됩니다. COM 클래스 템플릿을 새 클래스를 만들고 COM 개체로 클래스 및 상호 운용성 계층을 생성 하 고 운영 체제에 등록 하려면 프로젝트를 구성 합니다.  
  
> [!NOTE]
>  만든 클래스를 노출할 수도 있지만 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] COM 개체로 사용 하 여 비관리 코드를 실제 COM 개체 아니며에서 사용할 수 없는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다. 자세한 내용은 참조 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)합니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a>COM 클래스 템플릿을 사용 하 여 COM 개체를 만들려면  
  
1.  새 Windows 응용 프로그램 프로젝트를 열고는 **파일** 메뉴를 클릭 하 여 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자는 **프로젝트 형식** 필드에서 Windows가 선택 되었는지 확인 합니다. 선택 **클래스 라이브러리** 에서 **템플릿** 목록으로 이동한 다음 클릭 **확인**합니다. 새 프로젝트가 표시 됩니다.  
  
3.  선택 **새 항목 추가** 에서 **프로젝트** 메뉴. **새 항목 추가** 대화 상자가 표시됩니다.  
  
4.  선택 **COM 클래스** 에서 **템플릿** 목록으로 이동한 다음 클릭 **추가**합니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]새 클래스를 추가 하 고 COM interop에 대 한 새 프로젝트를 구성 합니다.  
  
5.  COM 클래스에 속성, 메서드 및 이벤트 등의 코드를 추가 합니다.  
  
6.  선택 **빌드 ClassLibrary1** 에서 **빌드** 메뉴. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]어셈블리를 빌드하고 운영 체제와 COM 개체를 등록 합니다.  
  
## <a name="creating-com-objects-without-the-com-class-template"></a>COM 클래스 템플릿 사용 하지 않고 COM 개체 만들기  
 COM 클래스 템플릿을 사용 하지 않고 수동으로 COM 클래스를 만들 수 있습니다. 이 절차는 명령줄에서 작업할 때 또는 COM 개체를 정의 하는 방법을 보다 더 많은 제어 하려는 경우 유용 합니다.  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a>COM 개체를 생성 하 여 프로젝트를 설정 하려면  
  
1.  새 Windows 응용 프로그램 프로젝트를 열고는 **파일** 메뉴를 클릭 하 여 **새 프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자는 **프로젝트 형식** 필드에서 Windows가 선택 되었는지 확인 합니다. 선택 **클래스 라이브러리** 에서 **템플릿** 목록으로 이동한 다음 클릭 **확인**합니다. 새 프로젝트가 표시 됩니다.  
  
3.  **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다. **프로젝트 디자이너** 표시 됩니다.  
  
4.  **컴파일** 탭을 클릭합니다.  
  
5.  선택 된 **COM Interop 등록** 확인란 합니다.  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a>COM 개체를 만들려면 클래스에 코드를 설정 하려면  
  
1.  **솔루션 탐색기**를 두 번 클릭 **Class1.vb** 해당 코드를 표시 합니다.  
  
2.  클래스 이름을 `ComClass1`로 바꿉니다.  
  
3.  다음 상수를 추가 `ComClass1`합니다. 전역적으로 고유 식별자 (GUID) 상수 COM 개체가 있어야 하는 저장 됩니다.  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  **도구** 메뉴에서 **GUID 만들기**를 클릭합니다. **GUID 만들기** 대화 상자에서 **레지스트리 형식**과 **복사**를 차례로 클릭합니다. **끝내기**를 클릭합니다.  
  
5.  빈 문자열을 바꾸기는 `ClassId` GUID를 가진 제거 하는 선행 및 후행 중괄호 합니다. 예를 들어 Guidgen에 의해 제공 된 GUID는 `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` 코드는 다음과 같아야 합니다.  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  에 대해 위의 단계를 반복 하는 `InterfaceId` 및 `EventsId` 다음 예제와 같이 상수입니다.  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  Guid는 새롭고 고유한; 되는지 확인 그렇지 않으면 COM 구성 요소는 다른 COM 구성 요소와 충돌할 수 있습니다.  
  
7.  추가 `ComClass` 특성을 `ComClass1`, 다음 예제와 같이 클래스 ID, 인터페이스 ID 및 이벤트 ID에 대 한 Guid를 지정 합니다.  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  COM 클래스에는 매개 변수가 없는 있어야 `Public Sub New()` 생성자 또는 클래스 올바르게 등록 되지 것입니다. 클래스에 매개 변수가 없는 생성자를 추가 합니다.  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. 속성, 메서드 및 이벤트에 추가 클래스를 사용 하 여 종료는 `End Class` 문. 선택 **솔루션 빌드** 에서 **빌드** 메뉴. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]어셈블리를 빌드하고 운영 체제와 COM 개체를 등록 합니다.  
  
    > [!NOTE]
    >  COM 개체를 생성 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 다른에서 사용할 수 없는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 응용 프로그램 진정한 COM 개체가 없기 때문에 있습니다. 이러한 COM 개체에 대 한 참조를 추가 하려는 시도 오류가 발생 합니다. 자세한 내용은 참조 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [연습: COM 개체를 사용한 상속 구현](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md)  
 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [상호 운용성 문제 해결](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
