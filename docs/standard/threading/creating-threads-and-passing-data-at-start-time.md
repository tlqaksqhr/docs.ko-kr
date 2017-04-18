---
title: "Creating Threads and Passing Data at Start Time | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "threading [.NET Framework], creating"
  - "threading [.NET Framework], passing data to threads"
  - "threading [.NET Framework], retrieving data from threads"
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Creating Threads and Passing Data at Start Time
운영 체제 프로세스가 만들어지면 운영 체제에서 원본 응용 프로그램 도메인을 포함하여 해당 프로세스에서 코드를 실행할 스레드를 삽입합니다.  이때부터 반드시 운영 체제 스레드를 만들거나 삭제하지 않아도 응용 프로그램 도메인을 만들고 삭제할 수 있습니다.  실행 중인 코드가 관리 코드인 경우 <xref:System.Threading.Thread> 형식의 정적 <xref:System.Threading.Thread.CurrentThread%2A> 속성을 검색하여 현재 응용 프로그램 도메인에서 실행 중인 스레드의 <xref:System.Threading.Thread> 개체를 가져올 수 있습니다.  이 항목에서는 스레드 만들기를 설명하고 데이터를 스레드 프로시저로 전달하는 대체 방법을 설명합니다.  
  
## 스레드 만들기  
 새 <xref:System.Threading.Thread> 개체를 만들면 관리되는 스레드가 새로 만들어집니다.  <xref:System.Threading.Thread> 클래스에 <xref:System.Threading.ThreadStart> 대리자 또는 <xref:System.Threading.ParameterizedThreadStart> 대리자를 사용하는 생성자가 있습니다. 대리자는 <xref:System.Threading.Thread.Start%2A> 메서드를 호출할 때 새 스레드가 호출하는 메서드를 래핑합니다.  <xref:System.Threading.Thread.Start%2A>를 두 번 이상 호출하면 <xref:System.Threading.ThreadStateException>이 throw됩니다.  
  
 <xref:System.Threading.Thread.Start%2A> 메서드는 새 스레드가 실제로 시작되기 전에 즉시 반환되는 경우가 종종 있습니다.  <xref:System.Threading.Thread.ThreadState%2A> 및 <xref:System.Threading.Thread.IsAlive%2A> 속성을 사용하여 언제든지 스레드의 상태를 결정할 수 있지만 스레드의 활동을 동기화하는 데 이러한 속성을 사용하면 안 됩니다.  
  
> [!NOTE]
>  스레드가 시작된 후에는 <xref:System.Threading.Thread> 개체에 대한 참조를 유지할 필요가 없습니다.  스레드는 스레드 프로시저가 종료될 때까지 계속 실행됩니다.  
  
 다음 코드 예제에서는 다른 개체의 인스턴스와 정적 메서드를 호출하기 위해 두 개의 새 스레드를 만듭니다.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## 데이터를 스레드에 전달 및 스레드에서 데이터 검색  
 .NET Framework 버전 2.0에서 <xref:System.Threading.ParameterizedThreadStart> 대리자는 <xref:System.Threading.Thread.Start%2A?displayProperty=fullName> 메서드 오버로드를 호출할 때 데이터를 포함하는 개체를 스레드에 간단하게 전달할 수 있는 방법을 제공합니다.  코드 예제를 보려면 <xref:System.Threading.ParameterizedThreadStart>를 참조하십시오.  
  
 <xref:System.Threading.Thread.Start%2A?displayProperty=fullName> 메서드 오버로드에서 모든 개체를 허용하기 때문에 <xref:System.Threading.ParameterizedThreadStart> 대리자를 사용하는 것은 데이터를 전달하는 데 있어 형식이 안전한 방법이 아닙니다.  대안은 스레드 프로시저 및 도우미 클래스의 데이터를 캡슐화하고 <xref:System.Threading.ThreadStart> 대리자를 사용하여 스레드 프로시저를 실행하는 것입니다.  이 방법은 다음 두 가지 코드 예제에서 보여 줍니다.  
  
 데이터를 비동기 호출로부터 반환할 장소가 없기 때문에 이러한 대리자 모두에 반환 값이 없습니다.  스레드 메서드의 결과를 검색하려면 두 번째 코드 예제에서와 같이 콜백 메서드를 사용합니다.  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### 콜백 메서드로 데이터 검색  
 다음 예제에서는 스레드에서 데이터를 검색하는 콜백 메서드를 보여 줍니다.  또한 데이터 및 스레드 메서드를 포함하는 클래스의 생성자는 콜백 메서드를 나타내는 대리자를 받아들이므로 스레드 메서드가 종료되기 전에 콜백 대리자를 호출합니다.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## 참고 항목  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadStart>   
 <xref:System.Threading.ParameterizedThreadStart>   
 <xref:System.Threading.Thread.Start%2A?displayProperty=fullName>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)