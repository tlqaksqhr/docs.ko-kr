---
title: "방법: 제네릭 형식 T가 DataRow가 아닌 CopyToDataTable&lt;T&gt; 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 제네릭 형식 T가 DataRow가 아닌 CopyToDataTable&lt;T&gt; 구현
대개 <xref:System.Data.DataTable> 개체는 데이터 바인딩에 사용됩니다.  <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 쿼리 결과를 받아서 나중에 데이터 바인딩에 사용할 수 있도록 데이터를 <xref:System.Data.DataTable>에 복사합니다.  하지만 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 제네릭 매개 변수 `T`가 <xref:System.Data.DataRow> 형식인 <xref:System.Collections.Generic.IEnumerable%601> 소스에서만 작동합니다.  이 제한은 유용하지만 이로 인해 일련의 스칼라 형식, 익명 형식을 프로젝션하는 쿼리 또는 테이블 조인을 수행하는 쿼리에서 테이블을 만들지 못하게 됩니다.  
  
 이 항목에서는 <xref:System.Data.DataRow> 형식 이외의 제네릭 매개 변수 `T` 형식을 사용할 수 있는 두 가지 사용자 지정 `CopyToDataTable<T>` 확장을 구현하는 방법을 설명합니다.  <xref:System.Collections.Generic.IEnumerable%601> 소스에서 <xref:System.Data.DataTable>을 만드는 로직은 `ObjectShredder<T>` 클래스에 있으며, 이 클래스는 두 오버로드 `CopyToDataTable<T>` 확장 메서드로 래핑됩니다.  `ObjectShredder<T>` 클래스의 `Shred` 메서드는 채워진 <xref:System.Data.DataTable>을 반환하며 세 개의 입력 매개 변수로 <xref:System.Collections.Generic.IEnumerable%601> 소스, <xref:System.Data.DataTable> 및 <xref:System.Data.LoadOption> 열거형을 사용합니다.  반환된 <xref:System.Data.DataTable>의 초기 스키마는 형식 `T`의 스키마에 기반합니다.  기존 테이블이 입력으로 제공되는 경우 해당 스키마는 형식 `T`의 스키마와 일치해야 합니다.  형식 `T`의 각 public 속성 및 필드는 반환된 테이블에서 <xref:System.Data.DataColumn>으로 변환됩니다.  소스 시퀀스에 `T`에서 파생된 형식이 포함되는 경우 추가 public 속성 또는 필드를 사용할 수 있도록 반환된 테이블 스키마가 확장됩니다.  
  
 사용자 지정 `CopyToDataTable<T>` 메서드를 사용하는 예제는 [쿼리에서 DataTable 만들기](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)를 참조하세요.  
  
### 응용 프로그램에서 사용자 지정 CopyToDataTable\<T\> 메서드를 구현하려면  
  
1.  <xref:System.Collections.Generic.IEnumerable%601> 소스에서 <xref:System.Data.DataTable>을 만드는 `ObjectShredder<T>` 클래스를 구현합니다.  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  
  
2.  클래스에서 사용자 지정 `CopyToDataTable<T>` 확장 메서드를 구현합니다.  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3.  응용 프로그램에 `ObjectShredder<T>` 클래스 및 `CopyToDataTable<T>` 확장 메서드를 추가합니다.  
  
    ```vb  
    Module Module1  
        Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
        End Sub  
    End Module  
  
    Public Module CustomLINQtoDataSetMethods  
    …  
    End Module  
  
    Public Class ObjectShredder(Of T)  
    …  
    End Class  
    ```  
  
4.  ```c#  
    class Program  
    {  
            static void Main(string[] args)  
            {  
               // Your application code using CopyToDataTable<T>.  
            }  
    }  
    public static class CustomLINQtoDataSetMethods  
    {  
    …  
    }  
    public class ObjectShredder<T>  
    {  
    …  
    }  
    ```  
  
## 참고 항목  
 [쿼리에서 DataTable 만들기](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)   
 [프로그래밍 가이드](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)