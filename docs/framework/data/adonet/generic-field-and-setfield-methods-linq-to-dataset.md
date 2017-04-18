---
title: "제네릭 필드 및 SetField 메서드(LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 제네릭 필드 및 SetField 메서드(LINQ to DataSet)
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]은 열 값에 액세스할 수 있도록 확장 메서드인 <xref:System.Data.DataRowExtensions.Field%2A> 메서드 및 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드를 <xref:System.Data.DataRow> 클래스에 제공합니다. 개발자는 이러한 메서드를 사용하여 열 값에 쉽게 액세스할 수 있으며, 특히 null 값과 관련된 작업을 쉽게 수행할 수 있습니다. <xref:System.Data.DataSet>은 <xref:System.DBNull.Value>를 사용하여 null 값을 나타내는 반면 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]에서는 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]에서 도입된 nullable 형식 지원을 사용합니다.  <xref:System.Data.DataRow>의 기존 열 접근자를 사용하려면 반환 개체를 적절한 형식으로 캐스팅해야 합니다.  반환된 <xref:System.DBNull.Value>가 암시적으로 다른 형식으로 캐스팅되면 <xref:System.InvalidCastException>이 throw되므로 <xref:System.Data.DataRow>의 특정 필드가 null일 가능성이 있는 경우 명시적으로 null 값을 확인해야 합니다.  다음 예제에서 <xref:System.Data.DataRow.IsNull%2A> 메서드를 사용하여 null 값을 확인하지 않으면 인덱서에서 <xref:System.DBNull.Value>를 반환하면서 <xref:System.String>으로 캐스팅할 때 예외가 throw됩니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 <xref:System.Data.DataRowExtensions.Field%2A> 메서드는 <xref:System.Data.DataRow>의 열 값에 대한 액세스를 제공하고 <xref:System.Data.DataRowExtensions.SetField%2A>는 <xref:System.Data.DataRow>의 열 값을 설정합니다.  이전 예제에서와 마찬가지로 <xref:System.Data.DataRowExtensions.Field%2A> 메서드와 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드에서 nullable 형식이 처리되므로 명시적으로 null 값을 검사하지 않아도 됩니다.  또한 두 메서드 모두 제네릭 메서드이므로 반환 형식을 캐스팅하지 않아도 됩니다.  
  
 다음 예제에서는 <xref:System.Data.DataRowExtensions.Field%2A> 메서드를 사용합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 <xref:System.Data.DataRowExtensions.Field%2A> 메서드 및 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드의 제네릭 매개 변수 `T`에 지정된 데이터 형식은 내부 값의 형식과 일치해야 합니다.  그렇지 않으면 <xref:System.InvalidCastException> 예외가 throw됩니다.  지정된 열 이름도 <xref:System.Data.DataSet>의 열 이름과 일치해야 하며, 그렇지 않으면 <xref:System.ArgumentException>이 throw됩니다.  두 경우 모두 쿼리가 실행되는 런타임에 데이터 열거형에서 예외가 throw됩니다.  
  
 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드 자체에서는 형식 변환이 수행되지 않습니다.  그렇다고 해서 형식 변환이 발생하지 않는다는 것은 아닙니다.  <xref:System.Data.DataRowExtensions.SetField%2A> 메서드는 <xref:System.Data.DataRow> 클래스의 [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] 동작을 노출합니다.  <xref:System.Data.DataRow> 개체에서 형식 변환을 수행하면 변환된 값은 <xref:System.Data.DataRow> 개체에 저장됩니다.  
  
## 참고 항목  
 <xref:System.Data.DataRowExtensions>