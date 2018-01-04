---
title: "방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택"
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
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de41d5664c2481032dffe213a52779834338ca2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택
종종 Windows 응용 프로그램을 만드는 경우 파일 집합을 저장하기 위해 사용자에게 폴더를 선택하도록 요구하는 메시지를 매우 빈번하게 표시해야 합니다. Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소를 사용 하면 쉽게이 작업을 수행할 수 있습니다.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더를 선택하려면  
  
1.  프로시저에서 확인 된 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.Form.DialogResult%2A> 속성 대화 상자를 닫은 방법을 보고의 값을 보려면는 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성.  
  
2.  집합에서 최상위 폴더 대화 상자의 트리 뷰 내에서 표시 되는 경우 설정 하는 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 속성의 멤버를 사용 하는 <xref:System.Environment.SpecialFolder> 열거형입니다.  
  
3.  또한, 설정할 수 있습니다는 <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> 폴더 브라우저 트리 보기의 상단에 표시 되는 텍스트 문자열을 지정 하는 속성입니다.  
  
     다음 예제에는 <xref:System.Windows.Forms.FolderBrowserDialog> Visual Studio에서 프로젝트를 만들 및에서 저장할 폴더를 선택 하 라는 메시지가 표시 되는 폴더를 선택한 구성 요소를 사용 합니다. 이 예제에서는 폴더 이름 다음에 표시 됩니다는 <xref:System.Windows.Forms.TextBox> 폼에서 컨트롤입니다. 와 같은 편집 가능한 영역에 위치를 배치 하는 것이 좋습니다는 <xref:System.Windows.Forms.TextBox> 제어 오류나 기타 문제가 발생할 경우 해당 선택 편집할 수 있도록 합니다. 이 예에서는 가정 된 폼을 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소와 <xref:System.Windows.Forms.TextBox> 제어 합니다.  
  
    ```vb  
    Public Sub ChooseFolder()  
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then  
            TextBox1.Text = FolderBrowserDialog1.SelectedPath  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    public void ChooseFolder()  
    {  
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)   
        {  
            textBox1.Text = folderBrowserDialog1.SelectedPath;  
        }  
    }  
    ```  
  
    ```cpp  
    public:  
       void ChooseFolder()  
       {  
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Text = folderBrowserDialog1->SelectedPath;  
          }  
       }  
    ```  
  
    > [!IMPORTANT]
    >  이 클래스를 사용 하려면 어셈블리 한 부여 권한 수준이 필요 하 여는 <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> 참가 하는 속성의는 <xref:System.Security.Permissions.FileIOPermissionAccess> 열거형입니다. 부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다. 자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하세요.  
  
 파일을 저장하는 방법에 대한 자세한 내용은 [방법: SaveFileDialog 구성 요소를 사용하여 파일 저장](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [FolderBrowserDialog 구성 요소 개요(Windows Forms)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)  
 [FolderBrowserDialog 구성 요소](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
