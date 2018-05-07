---
title: '방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 8f331c67dd22a6a9e2382ecc11d23c67cd2a5cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가
<xref:System.Windows.Forms.BindingNavigator> 컨트롤은 특수 한 용도의 <xref:System.Windows.Forms.ToolStrip> 탐색 하 고 데이터에 바인딩되는 양식에서 컨트롤을 조작 하는 데 사용 되는 컨트롤입니다.  
  
 이기 때문에 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 <xref:System.Windows.Forms.BindingNavigator> 사용자에 대 한 추가 또는 대체 명령을 포함 하도록 구성 요소를 쉽게 수정할 수 있습니다.  
  
 다음 절차에는 <xref:System.Windows.Forms.TextBox> 컨트롤이 데이터 바인딩되어 및 <xref:System.Windows.Forms.ToolStrip> 폼에 추가 되는 컨트롤 및 취소 단추를 로드, 저장, 포함 하도록 수정 됩니다.  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>부하를 추가 하려면 저장 및 취소 단추 BindingNavigator 구성 요소  
  
1.  폼에 <xref:System.Windows.Forms.TextBox> 컨트롤을 추가합니다.  
  
2.  에 바인딩합니다는 <xref:System.Windows.Forms.BindingSource>, 데이터 소스에 바인딩된 합니다. 이 예는 <xref:System.Windows.Forms.BindingSource> 데이터베이스에 바인딩되어 있습니다.  
  
3.  데이터 집합 및 테이블 어댑터를 생성 한 후 끌어서는 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 폼입니다.  
  
4.  설정의 <xref:System.Windows.Forms.BindingNavigator> 컨트롤의 <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 속성을는 <xref:System.Windows.Forms.BindingSource> 컨트롤에 바인딩된 폼에 있습니다.  
  
5.  <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 선택합니다.  
  
6.  스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 하므로 **BindingNavigator 작업** 대화 상자가 나타나고 선택 **항목편집**.  
  
     **항목 컬렉션 편집기** 나타납니다.  
  
7.  에 **항목 컬렉션 편집기**, 다음 단계를 완료 합니다.  
  
    1.  추가 <xref:System.Windows.Forms.ToolStripSeparator> 및 세 개의 <xref:System.Windows.Forms.ToolStripButton> 적절 한 유형을 선택 하 여 항목 <xref:System.Windows.Forms.ToolStripItem> 클릭 하 고는 **추가** 단추입니다.  
  
    2.  설정의 <xref:System.Windows.Forms.ToolStripItem.Name%2A> 속성에 있는 단추의**LoadButton**,**저장 단추**, 및**CancelButton**각각.  
  
    3.  설정의 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성에 있는 단추의**부하** `,` **저장**, 및**취소**합니다.  
  
    4.  설정의 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 각 단추에 대 한 속성**텍스트**합니다. 이 속성 설정할 수 있습니다 또는**이미지**또는**ImageAndText**에 표시할 이미지를 설정 하 고는 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성.  
  
    5.  클릭 **확인** 대화 상자를 닫습니다. 단추에 추가 되는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
8.  폼을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다.  
  
9. 코드 편집기에서 데이터 테이블 어댑터를 로드 하는 코드 줄을 찾습니다. 이 코드는 2 단계에서 데이터 바인딩을를 설정할 때 생성 되었습니다. 코드는 다음과 비슷해야: `TableAdapterName.Fill(DataSetName.TableName)`합니다. 양식의에 포함 될 가능성이 <xref:System.Windows.Forms.Form.Load> 이벤트입니다.  
  
10. 에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트는**부하** <xref:System.Windows.Forms.ToolStripButton> 앞에서 만든 하 고이 데이터 로드 코드 테이블로 이동 합니다.  
  
     코드 이제 다음과 같아야 합니다.  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. 에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트는 **저장** <xref:System.Windows.Forms.ToolStripButton> 앞에서 만든 고에 바인딩된 테이블 컨트롤 내에서 데이터를 업데이트 하는 코드를 작성 합니다.  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  일부 경우에는 <xref:System.Windows.Forms.BindingNavigator> 구성 요소는 이미는**저장** Windows Forms 디자이너에서 됩니다 생성 단추를 하지만 코드가 없습니다. 이 경우에 앞의 코드를 배치할 수 있습니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 에 새 단추를 만드는 하는 것이 아니라 해당 단추에 대 한 이벤트 처리기는 <xref:System.Windows.Forms.ToolStrip>합니다. 로 설정 해야 단추가 기본적으로 비활성화 하는 반면는 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 단추의 속성 `true` 단추 함수를 올바르게 있어야 합니다.  
  
12. 에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트는**취소** <xref:System.Windows.Forms.ToolStripButton> 앞에서 만든 하 고 표시 되는 데이터 레코드에 변경 내용을 취소 하는 코드를 작성 합니다.  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> 메서드는 데이터의 행으로 범위가 제한 됩니다. 다음 레코드로 이동 하기 전에 해당 개별 레코드를 보고 하는 동안 변경 내용을 저장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [BindingNavigator 컨트롤](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [BindingSource 구성 요소 개요](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
