---
title: "방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 조작"
  - "BindingNavigator 컨트롤[Windows Forms], 단추 추가"
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가
<xref:System.Windows.Forms.BindingNavigator> 컨트롤은 데이터에 바인딩된 컨트롤을 폼에서 탐색하고 조작하기 위한 특수 용도의 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.  
  
 이 컨트롤은 <xref:System.Windows.Forms.ToolStrip> 컨트롤이므로 <xref:System.Windows.Forms.BindingNavigator> 구성 요소를 간단하게 수정하여 구성 요소에 사용자를 위한 추가 명령이나 대체 명령을 포함할 수 있습니다.  
  
 다음 절차에서는 <xref:System.Windows.Forms.TextBox> 컨트롤을 데이터에 바인딩하고 폼에 추가된 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 로드, 저장 및 취소 단추가 포함되도록 수정할 수 있습니다.  
  
### BindingNavigator 구성 요소에 로드, 저장 및 취소 단추를 추가하려면  
  
1.  폼에 <xref:System.Windows.Forms.TextBox> 컨트롤을 추가합니다.  
  
2.  데이터 소스에 바인딩되는 <xref:System.Windows.Forms.BindingSource>에 컨트롤을 바인딩합니다.  이 예제에서는 <xref:System.Windows.Forms.BindingSource>가 데이터베이스에 바인딩됩니다.  
  
3.  데이터 집합 및 테이블 어댑터를 생성한 다음 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 폼으로 끌어 옵니다.  
  
4.  <xref:System.Windows.Forms.BindingNavigator> 컨트롤의 <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 속성을 컨트롤에 바인딩된 폼의 <xref:System.Windows.Forms.BindingSource>로 설정합니다.  
  
5.  <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 선택합니다.  
  
6.  스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)를 클릭하여 **BindingNavigator 작업** 대화 상자를 표시하고 **항목 편집**을 선택합니다.  
  
     **항목 컬렉션 편집기**가 나타납니다.  
  
7.  **항목 컬렉션 편집기**에서 다음을 수행합니다.  
  
    1.  <xref:System.Windows.Forms.ToolStripItem>의 적절한 형식을 선택하고 **추가** 단추를 클릭하여 <xref:System.Windows.Forms.ToolStripSeparator> 및 세 개의 <xref:System.Windows.Forms.ToolStripButton> 항목을 추가합니다.  
  
    2.  단추의 <xref:System.Windows.Forms.ToolStripItem.Name%2A> 속성을 각각 `LoadButton`, `SaveButton` 및 `CancelButton`으로 설정합니다.  
  
    3.  단추의 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `Load``, Save` 및 `Cancel`로 설정합니다.  
  
    4.  단추의 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 `Text`로 설정합니다.  또는 이 속성을 `Image` `` 또는 `ImageAndText`로 `` 설정하고 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성에 표시될 이미지를 설정할 수 있습니다.  
  
    5.  **확인**을 클릭하여 대화 상자를 닫습니다. 세 개의 단추가 <xref:System.Windows.Forms.ToolStrip>에 추가됩니다.  
  
8.  폼을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 선택합니다.  
  
9. 코드 편집기에서 데이터를 테이블 어댑터에 로드하는 코드 줄을 찾습니다.  이 코드는 2단계에서 데이터 바인딩을 설정할 때 생성되며  `TableAdapterName.Fill(DataSetName.TableName)`과 같은 형태여야 합니다.  이러한 형태는 주로 <xref:System.Windows.Forms.Form.Load> 이벤트에 있습니다.  
  
10. 이전에 만든 `` **Load** `` <xref:System.Windows.Forms.ToolStripButton>의 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트에 대한 이벤트 처리기를 만들고 이 데이터 로딩 코드를 이벤트 처리기로 이동합니다.  
  
     코드는 다음과 같습니다.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. 이전에 만든 **Save** `` <xref:System.Windows.Forms.ToolStripButton>의 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트에 대한 이벤트 처리기를 만들고 코드를 작성하여 컨트롤이 바인딩된 테이블에 있는 데이터를 업데이트합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingNavigator> 구성 요소에 이미 `` **Save** 단추가 있지만 Windows Forms 디자이너에서 코드가 생성되지는 않는 경우도 있습니다.  이 경우 <xref:System.Windows.Forms.ToolStrip>에 새 단추를 만드는 것이 아니라 해당 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트 처리기에 위의 코드를 배치할 수 있습니다.  그러나 단추는 기본적으로 비활성화되므로 단추가 제대로 작동하려면 단추의 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 속성을 `true`로 설정해야 합니다.  
  
12. 이전에 만든 `` **Cancel** `` <xref:System.Windows.Forms.ToolStripButton>의 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트에 대한 이벤트 처리기를 만들고 코드를 작성하여 표시된 데이터 레코드에 대한 모든 변경 내용을 취소합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> 메서드의 범위는 데이터 행까지입니다.  다음 레코드를 탐색하기 전에 표시된 개별 레코드에 대해 수행한 모든 변경 내용을 저장합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.ToolStrip>   
 [BindingNavigator 컨트롤](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [BindingSource 구성 요소 개요](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)