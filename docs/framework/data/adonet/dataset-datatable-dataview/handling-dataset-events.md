---
title: "데이터 집합 이벤트 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 데이터 집합 이벤트 처리
<xref:System.Data.DataSet> 개체는 <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized> 및 <xref:System.Data.DataSet.MergeFailed>의 세 가지 이벤트를 제공합니다.  
  
## MergeFailed 이벤트  
 `DataSet` 개체의 이벤트 중 가장 많이 사용되는 `MergeFailed` 이벤트는 병합하는 `DataSet` 개체의 스키마에서 충돌이 발생할 때 나타납니다. 이러한 충돌은 대상 및 소스 <xref:System.Data.DataRow>의 기본 키 값이 동일하고 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성이 `true`로 설정된 경우 발생합니다. 예를 들어 병합할 테이블의 기본 키 열이 두 `DataSet` 개체에 있는 테이블 간에서 서로 같으면 예외가 throw되고 `MergeFailed` 이벤트가 발생합니다.<xref:System.Data.MergeFailedEventArgs> 이벤트로 전달되는 `MergeFailed` 개체에는 두 <xref:System.Data.MergeFailedEventArgs.Conflict%2A> 개체 사이의 스키마에서 발생한 충돌을 식별하는 `DataSet` 속성과 충돌한 테이블 이름을 식별하는 <xref:System.Data.MergeFailedEventArgs.Table%2A> 속성이 있습니다.  
  
 다음 코드 단편에서는 `MergeFailed` 이벤트에 대한 이벤트 처리기를 추가하는 방법을 보여 줍니다.  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## Initialized 이벤트  
 <xref:System.Data.DataSet.Initialized> 이벤트는 `DataSet` 생성자가 `DataSet`의 새 인스턴스를 초기화한 후 발생합니다.  
  
 <xref:System.Data.DataSet.IsInitialized%2A>이 초기화를 완료하면 `true` 속성이 `DataSet`를 반환하고, 그렇지 않으면 `false`를 반환합니다.<xref:System.Data.DataSet.BeginInit%2A>의 초기화를 시작하는 `DataSet` 메서드는 <xref:System.Data.DataSet.IsInitialized%2A>를 `false`로 설정하고,<xref:System.Data.DataSet.EndInit%2A>의 초기화를 끝내는 `DataSet` 메서드는 이를 `true`로 설정합니다. 이러한 메서드는 [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 디자인 환경에서 다른 구성 요소가 사용하는 `DataSet`을 초기화하는 데 사용합니다. 사용자 코드에는 일반적으로 이러한 메서드를 사용하지 않습니다.  
  
## Disposed 이벤트  
 `DataSet`은 <xref:System.ComponentModel.MarshalByValueComponent> 메서드와 <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> 이벤트를 모두 노출하는 <xref:System.ComponentModel.MarshalByValueComponent.Disposed> 클래스에서 파생됩니다.<xref:System.ComponentModel.MarshalByValueComponent.Disposed>이벤트는 구성 요소에서 삭제된 이벤트를 수신하기 위해 이벤트 처리기를 추가합니다.<xref:System.ComponentModel.MarshalByValueComponent.Disposed>메서드가 호출될 때 코드를 실행하려는 경우 `DataSet`의 <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>이벤트를 사용할 수 있습니다.<xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>는 <xref:System.ComponentModel.MarshalByValueComponent>에서 사용한 리소스를 해제합니다.  
  
> [!NOTE]
>  `DataSet` 및 `DataTable` 개체는 <xref:System.ComponentModel.MarshalByValueComponent>에서 상속하며 원격 연결을 위해 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 지원합니다. 이 두 개체는 원격으로 연결할 수 있는 유일한 ADO.NET 개체입니다. 자세한 내용은 [Remote Objects](http://msdn.microsoft.com/ko-kr/515686e6-0a8d-42f7-8188-73abede57c58)을 참조하세요.  
  
 `DataSet` 작업에 사용할 수 있는 다른 이벤트에 대한 자세한 내용은 [DataTable 이벤트 처리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) 및 [DataAdapter 이벤트 처리](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md)을 참조하세요.  
  
## 참고 항목  
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [ADO.NET에서 데이터 검색 및 수정](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)