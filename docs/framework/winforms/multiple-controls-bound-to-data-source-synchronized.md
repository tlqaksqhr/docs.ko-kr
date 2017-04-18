---
title: "방법: 동일한 데이터 소스에 바인딩된 여러 컨트롤의 동기화 상태가 유지되도록 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms], 여러 바인딩"
  - "컨트롤[Windows Forms], 데이터 소스와 동기화"
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 동일한 데이터 소스에 바인딩된 여러 컨트롤의 동기화 상태가 유지되도록 설정
Windows Forms에서 데이터 바인딩과 관련된 작업을 수행할 때 여러 컨트롤이 동일한 데이터 소스에 바인딩되어 있는 경우가 종종 있습니다.  경우에 따라 각 컨트롤의 바인딩된 속성이 다른 컨트롤 및 데이터 소스와 동기화 상태를 유지하도록 하기 위해 추가 단계가 필요할 수 있습니다.  이러한 단계는 다음과 같은 두 가지 경우에 필요합니다.  
  
-   데이터 소스가 <xref:System.ComponentModel.IBindingList>를 구현하지 않아 <xref:System.ComponentModel.ListChangedType> 형식의 <xref:System.ComponentModel.IBindingList.ListChanged> 이벤트를 생성하지 않는 경우  
  
-   데이터 소스가 <xref:System.ComponentModel.IEditableObject>를 구현하는 경우  
  
 첫 번째의 경우 <xref:System.Windows.Forms.BindingSource>를 사용하여 컨트롤에 데이터 소스를 바인딩할 수 있습니다.  두 번째의 경우에는 <xref:System.Windows.Forms.BindingSource>를 사용하고 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트를 처리한 다음 연관된 <xref:System.Windows.Forms.BindingManagerBase>에서 <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A>를 호출합니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 <xref:System.Data.DataSet>의 동일한 열에 세 개의 컨트롤, 즉 텍스트 상자 컨트롤 두 개와 <xref:System.Windows.Forms.DataGridView> 컨트롤 한 개를 바인딩하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트를 처리하고, 한 텍스트 상자의 텍스트 값이 변경될 때 다른 텍스트 상자와 <xref:System.Windows.Forms.DataGridView> 컨트롤이 올바른 값으로 업데이트되도록 하는 방법도 보여 줍니다.  
  
 이 예제에서는 <xref:System.Windows.Forms.BindingSource>를 사용하여 데이터 소스와 컨트롤을 바인딩합니다.  또는 데이터 소스에 직접 컨트롤을 바인딩하고 폼의 <xref:System.Windows.Forms.Control.BindingContext%2A>에서 바인딩에 대한 <xref:System.Windows.Forms.BindingManagerBase>를 검색한 다음 <xref:System.Windows.Forms.BindingManagerBase>의 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> 이벤트를 처리할 수도 있습니다.  이 작업을 수행하는 방법의 예제는 <xref:System.Windows.Forms.BindingManagerBase>의 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> 이벤트에 대한 도움말 페이지를 참조하십시오.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## 코드 컴파일  
  
-   이 코드 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System>, <xref:System.Windows.Forms> 및 <xref:System.Drawing> 어셈블리에 대한 참조  
  
-   <xref:System.Windows.Forms.Form.Load> 이벤트가 처리된 폼과 해당 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 예제의 `InitializeControlsAndDataSource` 메서드를 호출하는 코드  
  
## 참고 항목  
 [방법: BindingSource 구성 요소를 사용하여 폼 간에 바인딩된 데이터 공유](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)   
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [데이터 바인딩과 관련된 인터페이스](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)   
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)