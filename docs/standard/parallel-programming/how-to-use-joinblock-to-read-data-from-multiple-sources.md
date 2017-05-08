---
title: "How to: Use JoinBlock to Read Data From Multiple Sources | Microsoft Docs"
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
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, joining blocks in"
  - "dataflow blocks, joining in TPL"
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Use JoinBlock to Read Data From Multiple Sources
이 문서는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 클래스를 사용하여 여러 원본으로 부터 데이터를 사용할 수 있을때 작업을 수행 하는 방법에 대해 설명합니다.  또한 여러 조인 블록 데이터 소스를 보다 효율적으로 공유할 수 있도록 non\-greedy를 사용하는 방법에 대해 보여줍니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리 \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName> 네임 스페이스\)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]과 함께 배포 되지 않습니다.  이 <xref:System.Threading.Tasks.Dataflow> 네임스페이스를 설치 할려면, [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]에서 프로젝트를 열고, 프로젝트 메뉴에서 **Manage NuGet Packages** 를 선택한 후, `Microsoft.Tpl.Dataflow` 패키지를 온라인에서 검색합니다.  
  
## 예제  
 다음 예제에서는 세 가지 자원 종류, `NetworkResource`, `FileResource`, 그리고 `MemoryResource` 에 대해 정의하고, 리소스를 사용할 수 있게 되면 작업을 수행 합니다.  이 예제는 첫 번째 작업을 수행하기 위해 `NetworkResource` 및 `MemoryResource` 쌍을 필요로 하고 두번째 작업을 수행하기 위해 `FileResource` 및 `MemoryResource` 쌍을 필요로 합니다.  이 예제에서는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 클래스를 사용하여 필요한 모든 리소스가 사용가능할 때 이러한 작업을 수행할 수 있도록 합니다.  <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 개체가 모든 원본에서 데이터를 수신하는 경우, 이것은 해당 데이터를 이것의 대상에 전파합니다. 이 예제의 경우 대상은 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체입니다.  두 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 개체들은 `MemoryResource` 개체의 공유된 풀로 부터 읽습니다.  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 이 예제는 `MemoryResource` 개체의 공유 풀을 효율적으로 사용하기 위해서 non\-greedy 모드에서 동작하는 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 개체를 생성하기 위해 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> 속성을 `False` 로 가지는 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> 개체를 지정합니다.  Non\-greedy 조인 블록은 각 소스로 부터 하나가 유효할 때 까지 들어오는 모든 메시지를 연기 합니다.  연기된 메세지가 다른 블록에서 사용된 경우, 조인 블록이 프로세스를 재 시작 합니다.  Non\-greedy 모드는 조인 블록이 다른 블록이 데이터를 기다릴 때 하나 이상의 원본 블록을 공유하여 앞으로 진행을 하도록 해줍니다.  이 예제에서 `MemoryResource` 개체가 `memoryResources` 풀에 추가되는 경우, 두번째 데이터 소스를 수신할 첫 번째 조인 블록은 앞으로 진행할 수 있습니다.  만약 이 예제가 기본값인 greedy 모드를 사용했다면, 하나의 조인 블록은 `MemoryResource` 개체를 사용하고 두 번째 리소스를 사용할 수 있을 때까지 기다립니다.  그러나, 만약 다른 조인 블록이 두 번째 데이터 소스를 사용할 수 있을 경우, 이것은 `MemoryResource` 개체가 다른 조인 블록에 의해 사용되었기 때문에 앞으로 진행할 수 없습니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나 `DataflowNonGreedyJoin.cs` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 `DataflowNonGreedyJoin.vb`\) 파일에 붙여넣은 다음 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**  
  
## 강력한 프로그래밍  
 Non\-greedy 조인의 사용은 응용 프로그램에서 교착 상태를 방지하도록 도와줍니다.  소프트웨어 응용 프로그램에서는 둘 이상의 프로세스에서 각각 리소스를 보유하는 경우 다른 프로세스가 일부 다른 리소스를 해제하기를 서로 기다릴 때 *교착 상태*가 발생합니다.  두 개의 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 개체를 정의하는 응용 프로그램을 고려해 봅니다.  두 개체는 두 공유된 소스 블록에서 데이터를 읽습니다.  Greedy 모드에서 한 조인 블록이 첫 번째 소스에서 읽고 두 번째 조인 블록이 두번째 원본에서 읽을 경우, 둘 다 리소스가 다른 한쪽으로 부터 해제 되기를 서로 기다리기 때문에 응용 프로그램은 교착 상태가 발생하게 됩니다.  Non\-greedy 모드에서는 각 조인 블록은 모든 데이터를 사용할 수 있는 경우에만 소스로 부터 읽기 때문에 교착 상태의 위험이 제거 됩니다.  
  
## 참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)