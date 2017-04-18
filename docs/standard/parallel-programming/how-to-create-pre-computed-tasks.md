---
title: "How to: Create Pre-Computed Tasks | Microsoft Docs"
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
  - "tasks, creating pre-computed"
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Create Pre-Computed Tasks
이 문서에서는 <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=fullName> 메서드를 사용하여 캐시에 저장된 비동기 다운로드 작업 결과를 검색하는 방법을 설명합니다.  <xref:System.Threading.Tasks.Task.FromResult%2A> 메서드는 제공된 값을 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성으로 가지는 완료된 <xref:System.Threading.Tasks.Task%601> 개체를 반환합니다.  이 메서드는 <xref:System.Threading.Tasks.Task%601> 개체가 반환되는 비동기 작업을 수행하고 해당 <xref:System.Threading.Tasks.Task%601> 개체의 결과가 계산되어 있을 때 유용합니다.  
  
## 예제  
 다음 예제에서는 문자열을 웹에서 다운로드합니다.  이것은 `DownloadStringAsync` 메서드를 정의합니다.  이 메서드는 문자열을 웹에서 비동기적으로 다운로드 합니다.  또한 이 예제에서는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>개체를 사용하여 이전 작업의 결과를 캐시에 저장합니다.  만약 입력 주소가 이 캐시에서 유지되는 경우, `DownloadStringAsync` 은 <xref:System.Threading.Tasks.Task.FromResult%2A> 메서드를 사용하여 해당 주소의 콘텐츠를 보유하는 <xref:System.Threading.Tasks.Task%601> 개체를 생성합니다.  그렇지 않으면 `DownloadStringAsync` 은 파일을 웹에서 다운로드하고 캐시에 결과를 추가합니다.  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 이 예제에서는 여러 문자열을 다운로드 하는데 필요한 시간을 두 번 계산 합니다.  다운로드 작업의 두 번째 세트는 결과가 캐시에 보관 되어 있기 때문에 첫 번째 보다 더 짧은 시간을 취해야 합니다.  <xref:System.Threading.Tasks.Task.FromResult%2A> 메서드는 `DownloadStringAsync` 메서드를 사용하여 미리 계산된 결과들을 포함하는 <xref:System.Threading.Tasks.Task%601> 개체를 생성합니다.  
  
## 코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나 `CachedDownloads.cs` \([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 의 `CachedDownloads.vb`\) 파일에 붙여넣은 다음 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe CachedDownloads.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe CachedDownloads.vb**  
  
## 강력한 프로그래밍  
  
## 참고 항목  
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)