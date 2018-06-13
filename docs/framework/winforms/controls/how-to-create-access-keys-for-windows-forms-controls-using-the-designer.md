---
title: '방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 선택키 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 023973e7fa4ab1e8b802d8c7cd8abef8201ed720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532553"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 선택키 만들기
*선택 키* 은 메뉴, 메뉴 항목 또는 예: 단추 컨트롤의 레이블 텍스트에 밑줄이 그어진된 문자. "단추를 클릭"는 미리 정의 된 선택 키와 함께에서 ALT 키를 눌러 사용자 수 있습니다. 예를 들어, 단추는 폼을 인쇄 하는 프로시저를 실행 하는 경우 일부 이므로 해당 `Text` "Print" 추가 앰퍼샌드 (&) "P" 하면 문자 "P"에 밑줄이 단추 텍스트의 런타임 시 문자 앞에 속성을 설정 합니다. 사용자는 ALT + P를 눌러 단추와 연결 된 명령을 실행할 수 있습니다. 포커스를 받을 수 없는 컨트롤에 대 한 선택 키를 사용할 수 없습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-create-an-access-key-for-a-control"></a>컨트롤에 대 한 선택 키를 만들려면  
  
1.  에 **속성** 창의 설정의 `Text` 앰퍼샌드가 포함 하는 문자열 (&) 앞에 대 한 액세스 키가 될 속성입니다. 예를 들어 문자 "P" 선택 키를 설정 하려면 입력 **인쇄 &** ड आ 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Button>  
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
