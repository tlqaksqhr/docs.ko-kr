---
title: "방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 집합에 있는 오류 보기 | Microsoft Docs"
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
  - "오류 메시지, 데이터 집합에서 보기"
  - "ErrorProvider 구성 요소[Windows Forms], 데이터 집합 오류"
  - "오류[Windows Forms], 데이터 집합 오류"
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 집합에 있는 오류 보기
Windows Forms <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 사용하여 데이터 집합이나 기타 데이터 소스 내에 있는 열 오류를 볼 수 있습니다.  폼에 데이터 오류를 표시하기 위해 <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 컨트롤에 직접 연결할 필요는 없습니다.  이 구성 요소가 데이터 소스에 바인딩되면 동일한 데이터 소스에 바인딩되어 있는 컨트롤 옆에 오류 아이콘을 표시할 수 있습니다.  
  
> [!NOTE]
>  런타임에 오류 공급자의 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 및 <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> 속성을 변경하면 충돌 방지를 위해 <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> 메서드를 사용해야 합니다.  
  
### 데이터 오류를 표시하려면  
  
1.  구성 요소를 데이터 테이블의 특정 열에 바인딩합니다.  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
  
    ```  
  
2.  <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 속성을 폼에 설정합니다.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
  
    ```  
  
3.  현재 레코드의 위치를 열 오류가 있는 행으로 설정합니다.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
  
    ```  
  
## 참고 항목  
 [ErrorProvider 구성 요소 개요](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)   
 [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)