---
title: "방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기 | Microsoft Docs"
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
  - "선택키, 컨트롤 만들기"
  - "선택키, Windows Forms"
  - "컨트롤[Windows Forms], 선택키"
  - "대화 상자 컨트롤, 니모닉"
  - "바로 가기 키, 컨트롤 만들기"
  - "Label 컨트롤[Windows Forms], 선택키 만들기"
  - "니모닉"
  - "니모닉, 대화 상자 컨트롤에 추가"
  - "UseMnemonic 속성, Label 컨트롤"
  - "Windows Forms 컨트롤, 선택키"
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기
Windows Forms <xref:System.Windows.Forms.Label> 컨트롤을 사용하여 다른 컨트롤의 선택키를 지정할 수 있습니다.  label 컨트롤에서 선택키를 지정한 경우 Alt 키와 지정한 문자를 누르면 탭 순서대로 컨트롤의 포커스를 이동할 수 있습니다.  레이블은 포커스를 받지 못하기 때문에 자동으로 탭 순서에 따라 포커스가 다음 컨트롤로 이동합니다.  이 기법을 사용하여 텍스트 상자, 콤보 상자, 목록 상자 및 데이터 표에 선택키를 지정할 수 있습니다.  
  
### 레이블을 사용하여 컨트롤에 선택키를 지정하려면  
  
1.  먼저 레이블을 그린 다음 다른 컨트롤을 그립니다.  
  
     또는  
  
     컨트롤을 순서에 관계없이 그리고 레이블의 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 다른 컨트롤보다 1 작게 설정합니다.  
  
2.  레이블의 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true`로 설정합니다.  
  
3.  레이블의 <xref:System.Windows.Forms.Label.Text%2A> 속성에서 앰퍼샌드\(&\)를 사용하여 레이블의 선택키를 지정합니다.  자세한 내용은 [Windows Forms 컨트롤에 대한 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)를 참조하십시오.  
  
    > [!NOTE]
    >  선택키를 만드는 데 사용하는 것 외에도 label 컨트롤에서 앰퍼샌드를 표시해야 하는 경우가 있습니다.  예를 들어, 앰퍼샌드를 포함한 데이터가 있는 레코드 집합의 필드에 label 컨트롤을 바인딩하는 경우입니다.  label 컨트롤에 앰퍼샌드를 표시하려면 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `false`로 설정합니다.  앰퍼샌드도 표시하고 선택키도 사용하려면 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 속성을 `true`로 설정한 다음 선택키를 나타낼 경우 하나의 앰퍼샌드\(&\)를 사용하고, 앰퍼샌드를 표시할 경우 두 개의 앰퍼샌드를 사용합니다.  
  
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
  
## 참고 항목  
 [방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)   
 [Label 컨트롤 개요](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Label 컨트롤](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)