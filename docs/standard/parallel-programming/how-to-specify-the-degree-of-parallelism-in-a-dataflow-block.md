---
title: "방법: 데이터 흐름 블록의 병렬 처리 수준 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1ccd64a9acbc75a30984719671af2dc7dda6922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a>방법: 데이터 흐름 블록의 병렬 처리 수준 지정
이 문서에서는 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> 속성을 설정하여 실행 데이터 흐름 블록이 한 번에 둘 이상의 메시지를 처리할 수 있도록 하는 방법을 설명합니다. 이 방법은 오래 실행되는 계산을 수행하는 데이터 흐름 블록이 있고 메시지를 병렬로 처리하면 혜택을 얻을 수 있는 경우에 유용합니다. 이 예제에서는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> 클래스를 사용하여 여러 데이터 흐름 작업을 동시에 수행합니다. 하지만 TPL 데이터 흐름 라이브러리에서 제공하는 미리 정의된 실행 블록 형식인 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>에서 최대 병렬 처리 수준을 지정할 수 있습니다.  
  
> [!TIP]
>  TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다. 설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 가지 데이터 흐름 계산을 수행하고 각 계산에 필요한 경과 시간을 출력합니다. 첫 번째 계산에서는 최대 병렬 처리 수준을 기본값 1로 지정합니다. 최대 병렬 처리 수준이 1이면 데이터 흐름 블록이 메시지를 연속적으로 처리합니다. 두 번째 계산은 사용 가능한 프로세서 수와 동일한 최대 병렬 처리 수준을 지정하는 점을 제외하고 첫 번째 계산과 유사합니다. 이러한 지정에 따라 데이터 흐름 블록이 여러 작업을 병렬로 수행할 수 있습니다.  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여 넣거나, `DataflowDegreeOfParallelism.cs`([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `DataflowDegreeOfParallelism.vb`) 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 기본적으로 미리 정의된 각각의 데이터 흐름 블록은 메시지를 받은 순서대로 메시지를 전파합니다.  1보다 큰 최대 병렬 처리 수준을 지정하는 경우 여러 메시지가 동시에 처리되지만 메시지는 수신된 순서대로 전파됩니다.  
  
 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> 속성이 최대 병렬 처리 수준을 나타내기 때문에 데이터 흐름 블록은 지정한 것보다 낮은 병렬 처리 수준으로 실행될 수 있습니다. 데이터 흐름 블록은 기능적 요구 사항을 충족하기 위해서나 사용 가능한 시스템 리소스의 부족 때문에 낮은 병렬 처리 수준을 사용할 수 있습니다. 데이터 흐름 블록은 지정한 것보다 높은 병렬 처리 수준을 선택하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
