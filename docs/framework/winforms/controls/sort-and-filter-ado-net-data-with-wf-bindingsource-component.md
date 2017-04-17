---
title: "방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링 | Microsoft Docs"
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
  - "ADO.NET[Windows Forms]"
  - "BindingSource 구성 요소[Windows Forms], 데이터 정렬 및 필터링"
  - "데이터[Windows Forms], 필터링"
  - "데이터[Windows Forms], 정렬"
  - "데이터 정렬, ADO.NET"
  - "필터링[Windows Forms], ADO.NET"
  - "데이터 정렬"
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링
<xref:System.Windows.Forms.BindingSource.Sort%2A> 및 <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성을 통해 <xref:System.Windows.Forms.BindingSource> 컨트롤의 정렬 및 필터링 기능을 노출할 수 있습니다.  내부 데이터 소스가 <xref:System.ComponentModel.IBindingList>일 때는 간단한 정렬을 적용하고 데이터 소스가 <xref:System.ComponentModel.IBindingListView>일 때는 고급 정렬 및 필터링을 적용할 수 있습니다.  <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성에는 표준 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 구문이 필요합니다. 이 구문에서는 데이터 소스의 데이터 열 이름을 나타내는 문자열 뒤에 `ASC` 또는 `DESC`를 사용하여 목록을 오름차순으로 정렬할지 아니면 내림차순으로 정렬할지를 나타냅니다.  쉼표 구분 기호로 각 열을 구분하여 고급 정렬 또는 여러 열 정렬을 설정할 수 있습니다.  <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성에는 문자열 식을 사용합니다.  
  
> [!NOTE]
>  연결 문자열에 중요한 정보\(예: 암호\)를 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.  데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.  자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)을 참조하십시오.  
  
### BindingSource를 사용하여 데이터를 필터링하려면  
  
-   <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성을 원하는 식으로 설정합니다.  
  
     다음 코드 예제에서는 열 이름과 해당 열에 사용할 값으로 식이 구성됩니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### BindingSource를 사용하여 데이터를 정렬하려면  
  
1.  열 이름 뒤에 오름차순인지 내림차순인지 나타내는 `ASC` 또는 `DESC`가 오도록 <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성을 설정합니다.  
  
2.  열을 여러 개 사용할 때는 쉼표로 각각 구분합니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## 예제  
 다음 코드 예제에서는 Northwind 샘플 데이터베이스의 Customers 테이블의 데이터를 <xref:System.Windows.Forms.DataGridView> 컨트롤에 로드하고 표시되는 데이터를 필터링 및 정렬합니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## 코드 컴파일  
 이 예제를 실행하려면 이름이 `BindingSource1`인 <xref:System.Windows.Forms.BindingSource>와 이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView>가 들어 있는 폼에 코드를 붙여넣습니다.  폼에 대한 <xref:System.Windows.Forms.Form.Load> 이벤트를 처리하고 load 이벤트 처리기 메서드에서 `InitializeSortedFilteredBindingSource`를 호출합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>   
 <xref:System.Windows.Forms.BindingSource.Filter%2A>   
 [방법: 샘플 데이터베이스 설치](../Topic/How%20to:%20Install%20Sample%20Databases.md)   
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)