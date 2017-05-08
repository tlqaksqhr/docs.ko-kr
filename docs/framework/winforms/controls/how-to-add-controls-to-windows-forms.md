---
title: "방법: Windows Forms에 컨트롤 추가 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 추가"
  - "Windows Forms 컨트롤, 폼에 추가"
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms에 컨트롤 추가
대부분의 폼은 폼 화면에 컨트롤을 추가하는 방식으로 디자인하여 UI\(사용자 인터페이스\)를 정의합니다.  *컨트롤*은 정보를 표시하거나 사용자 입력을 받아들이는 데 사용되는 폼의 구성 요소입니다.  컨트롤에 대한 자세한 내용은 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 폼에 컨트롤을 그리려면  
  
1.  폼을 엽니다.  자세한 내용은 [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/ko-kr/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)를 참조하십시오.  
  
2.  **도구 상자**에서 폼에 추가할 컨트롤을 클릭합니다.  
  
3.  폼에서 컨트롤의 왼쪽 위 모퉁이가 위치할 지점을 클릭한 다음 컨트롤의 오른쪽 아래 모퉁이가 위치할 지점까지 끕니다.  
  
     지정된 위치 및 크기로 컨트롤이 추가됩니다.  
  
    > [!NOTE]
    >  각 컨트롤은 기본 크기가 정의되어 있습니다.  **도구 상자**에서 폼으로 컨트롤을 끌어 오면 기본 크기의 컨트롤을 폼에 추가할 수 있습니다.  
  
### 컨트롤을 폼으로 끌어 오려면  
  
1.  폼을 엽니다.  자세한 내용은 [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/ko-kr/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)를 참조하십시오.  
  
2.  **도구 상자**에서 원하는 컨트롤을 클릭한 다음 폼으로 끌어 옵니다.  
  
     지정된 위치에 기본 크기의 컨트롤이 추가됩니다.  
  
    > [!NOTE]
    >  **도구 상자**에서 컨트롤을 두 번 클릭하면 폼의 왼쪽 위 모퉁이에 기본 크기의 컨트롤을 추가할 수 있습니다.  
  
     런타임에 동적으로 컨트롤을 폼에 추가할 수도 있습니다.  다음 코드 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤을 클릭할 경우 <xref:System.Windows.Forms.TextBox> 컨트롤이 폼에 추가됩니다.  
  
    > [!NOTE]
    >  다음 절차를 수행하려면 **Button** 컨트롤 `Button1`이 이미 배치되어 있는 폼이 있어야 합니다.  
  
### 프로그래밍 방식으로 폼에 컨트롤을 추가하려면  
  
1.  폼의 클래스에서 단추의 `Click` 이벤트를 처리하는 메서드에 다음과 비슷한 코드를 삽입하여 컨트롤 변수에 참조를 추가한 다음, 컨트롤의 `Location`을 설정하고, 컨트롤을 추가합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  컨트롤의 다른 속성을 초기화하는 코드를 추가할 수도 있습니다.  
  
    > [!IMPORTANT]
    >  악의적인 `UserControl`을 참조하면 네트워크를 통해 로컬 컴퓨터가 보안 위험에 노출될 수 있습니다.  악의를 가진 사람이 유해한 사용자 지정 컨트롤을 만들고 개발자가 실수로 프로젝트에 이 컨트롤을 추가하는 경우에만 이러한 문제가 발생합니다.  
  
## 참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)   
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [방법: Windows Forms에서 컨트롤의 크기 조정](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)   
 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)