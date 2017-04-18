---
title: "방법: 개체의 초기화 지연 수행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET의 초기화 지연, 수행 방법"
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 개체의 초기화 지연 수행
<xref:System.Lazy%601?displayProperty=fullName> 클래스를 사용하면 초기화 지연을 수행하고 개체를 인스턴스화하는 작업을 쉽게 수행할 수 있습니다.  지연 방식으로 개체를 초기화하면 필요하지 않은 개체를 전혀 만들지 않아도 되며 개체에 처음으로 액세스할 때까지 그 초기화를 미룰 수 있습니다.  자세한 내용은 [초기화 지연](../../../docs/framework/performance/lazy-initialization.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 <xref:System.Lazy%601>을 사용하여 값을 초기화하는 방법을 보여 줍니다.  여기서는 `someCondition` 변수를 true 또는 false로 설정하는 다른 코드에 따라 지연 변수의 필요 여부가 결정되는 것으로 가정합니다.  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;    
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
{  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
}  
```  
  
## 예제  
 다음 예제에서는 <xref:System.Threading.ThreadLocal%601?displayProperty=fullName> 클래스를 사용하여 현재 스레드의 현재 개체 인스턴스에만 표시되는 형식을 초기화하는 방법을 보여 줍니다.  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## 참고 항목  
 <xref:System.Threading.LazyInitializer?displayProperty=fullName>   
 [초기화 지연](../../../docs/framework/performance/lazy-initialization.md)