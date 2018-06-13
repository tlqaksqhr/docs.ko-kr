---
title: '방법: Windows Forms 컨트롤에 대한 선택키 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 53ffd3632ff3e1179a72f1e2bfe4ea366e28b0f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530951"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>방법: Windows Forms 컨트롤에 대한 선택키 만들기
*선택 키* 은 메뉴, 메뉴 항목 또는 예: 단추 컨트롤의 레이블 텍스트에 밑줄이 그어진된 문자. 액세스 키가 있는 사용자 "" 단추를 클릭 수 미리 정의 된 선택 키와 함께에서 ALT 키를 눌러 합니다. 예를 들어, 단추는 폼을 인쇄 하는 프로시저를 실행 하는 경우 일부 이므로 해당 `Text` 속성이 "Print"로 설정 된 "p" 하면 "P" 단추 텍스트에는 런타임 시 밑줄이 그어집니다 전에 앰퍼샌드를 추가 합니다. 사용자는 ALT + P를 눌러 단추와 연결 된 명령을 실행할 수 있습니다. 포커스를 받을 수 없는 컨트롤에 대 한 선택 키를 사용할 수 없습니다.  
  
### <a name="to-create-an-access-key-for-a-control"></a>컨트롤에 대 한 선택 키를 만들려면  
  
1.  설정의 `Text` 앰퍼샌드가 포함 하는 문자열 (&) 문자 바로 가기로 속성입니다.  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  앰퍼샌드 캡션에 해지지 않도록 선택 키를 포함 하려면 앰퍼샌드를 두 번 포함 (& &). 앰퍼샌드 캡션에 나타나고 문자를 사용 하지는 밑줄이 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Button>  
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
