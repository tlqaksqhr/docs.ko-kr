---
title: "방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ad6cd99a6399adea2e69cbf844b9f134d2e592e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기
Windows Forms <xref:System.Windows.Forms.Label> 다른 컨트롤에 대 한 선택 키를 정의 하려면 컨트롤을 사용할 수 있습니다. 레이블 컨트롤에 선택 키를 정의할 때 사용자 ALT 키와 탭 순서에서 그 다음에 오는 컨트롤에 포커스를 이동 하도록 지정한 문자를 누를 수 있습니다. 레이블 포커스를 받을 수 없는 때문에 포커스가 탭 순서의 다음 컨트롤로 자동으로 이동 합니다. 이 기술을 사용 하 여 액세스 키 입력란, 콤보 상자, 목록 상자 및 데이터 표를 할당 합니다.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>레이블이 컨트롤 선택 키를 할당 하려면  
  
1.  먼저, 레이블을 그린 하 한 다음 다른 컨트롤을 그립니다.  
  
     또는  
  
     순서에 관계 없이 컨트롤을 그리고 설정는 <xref:System.Windows.Forms.Control.TabIndex%2A> 는 다른 컨트롤과 보다 1 작은 레이블의 속성입니다.  
  
2.  레이블을 설정 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true`합니다.  
  
3.  앰퍼샌드를 사용 하 여 (&)는 레이블에 <xref:System.Windows.Forms.Label.Text%2A> 레이블에 대 한 선택 키에 할당할 속성입니다. 자세한 내용은 참조 [만드는 액세스 키에 대 한 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)합니다.  
  
    > [!NOTE]
    >  선택 키를 만드는 데 사용할 보다는 label 컨트롤에서 앰퍼샌드를 표시 수 있습니다. 이 데이터 앰퍼샌드를 포함 하는 위치 레코드 집합에서 필드 레이블 컨트롤을 바인딩하는 경우에 발생할 수 있습니다. 레이블 컨트롤에 앰퍼샌드를 표시 하려면 설정는 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `false`합니다. 앰퍼샌드를 표시 및 선택 키를 갖게 하려는 경우 설정의 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true` 하나의 앰퍼샌드를 사용 하 여 액세스 키를 나타냅니다 (&) 및 앰퍼샌드를 앰퍼샌드를 두 번 표시할 합니다.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [Label 컨트롤 개요](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [레이블 컨트롤](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
