---
title: "방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "디렉터리[Windows Forms], 선택"
  - "디렉터리[Windows Forms], 선택"
  - "FolderBrowserDialog 구성 요소[Windows Forms], 디렉터리 선택"
  - "폴더[Windows Forms], 선택"
  - "폴더[Windows Forms], 선택"
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택
Windows 응용 프로그램을 만들 경우 주로 파일 집합을 저장하기 위해 사용자가 폴더를 선택할 수 있는 대화 상자를 표시해야 합니다.  Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소를 사용하면 이 작업을 손쉽게 수행할 수 있습니다.  
  
### FolderBrowserDialog 구성 요소를 사용하여 폴더를 선택하려면  
  
1.  프로시저에서 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.Form.DialogResult%2A> 속성을 검토하여 대화 상자를 어떻게 닫았는지 확인하고 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성 값을 가져옵니다.  
  
2.  대화 상자의 트리 뷰에서 맨 위에 나타낼 폴더를 설정해야 할 경우에는 [SpecialFolder](frlrfSystemEnvironmentSpecialFolderClassTopic) 열거형의 멤버를 사용하는 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 속성을 설정합니다.  
  
3.  또한 <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> 속성을 설정하여 폴더 브라우저 트리 뷰의 맨 위에 표시되는 텍스트 문자열을 지정할 수 있습니다.  
  
     아래 예제에서는 Visual Studio에서 프로젝트를 만든 후 저장할 폴더를 선택하는 경우와 같이 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소를 사용하여 폴더를 선택합니다.  그런 다음 폼의 <xref:System.Windows.Forms.TextBox> 컨트롤에 폴더 이름이 표시됩니다.  오류 또는 다른 문제가 발생할 경우 사용자가 직접 편집할 수 있도록 <xref:System.Windows.Forms.TextBox> 컨트롤과 같이 편집 가능한 영역에 표시하는 것이 좋습니다.  이 예제에서는 폼에 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소와 <xref:System.Windows.Forms.TextBox> 컨트롤이 있다고 가정합니다.  
  
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
    >  이 클래스를 사용하려면 어셈블리에 [FileIOPermissionAttribute.PathDiscoveryProperty](frlrfSystemSecurityPermissionsFileIOPermissionAttributeClassPathDiscoveryTopic) 속성에서 허용하는 수준의 권한이 있어야 합니다. 이 권한 수준은 <xref:System.Security.Permissions.FileIOPermissionAccess> 열거형에 속합니다.  부분 신뢰 컨텍스트에서 실행 중인 경우에는 권한이 부족하여 프로세스에서 예외를 throw할 수 있습니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../../../../docs/framework/misc/code-access-security-basics.md)을 참조하십시오.  
  
 파일을 저장하는 방법에 대한 내용은 [방법: SaveFileDialog 구성 요소를 사용하여 파일 저장](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.FolderBrowserDialog>   
 [FolderBrowserDialog 구성 요소 개요\(Windows Forms\)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)   
 [FolderBrowserDialog 구성 요소](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)