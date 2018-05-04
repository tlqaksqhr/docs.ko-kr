---
title: '방법: 미리 계산된 작업 만들기'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ce34e609dc9b1e2a5f1822ce27f65be74a636c86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-pre-computed-tasks"></a>방법: 미리 계산된 작업 만들기
이 문서에서는 <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> 메서드를 사용하여 캐시에 저장된 비동기 다운로드 작업의 결과를 검색하는 방법을 설명합니다. <xref:System.Threading.Tasks.Task.FromResult%2A> 메서드는 제공된 값을 <xref:System.Threading.Tasks.Task%601> 속성으로 포함하는 완료된 <xref:System.Threading.Tasks.Task%601.Result%2A> 개체를 반환합니다. 이 메서드는 <xref:System.Threading.Tasks.Task%601> 개체가 반환되는 비동기 작업을 수행하고 해당 <xref:System.Threading.Tasks.Task%601> 개체의 결과가 계산되어 있을 때 유용합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 웹에서 문자열을 다운로드합니다. 이 예제에서는 `DownloadStringAsync` 메서드를 정의합니다. 이 메서드는 웹에서 문자열을 비동기적으로 다운로드합니다. 또한 이 예제에서는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>개체를 사용하여 이전 작업의 결과를 캐시합니다. 입력 주소가 이 캐시에 저장된 경우 `DownloadStringAsync`는 <xref:System.Threading.Tasks.Task.FromResult%2A> 메서드를 사용하여 해당 주소의 콘텐츠를 포함하는 <xref:System.Threading.Tasks.Task%601> 개체를 생성합니다. 그렇지 않은 경우에는 `DownloadStringAsync`가 웹에서 파일을 다운로드하고 결과를 캐시에 추가합니다.  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 이 예제에서는 여러 문자열을 두 번 다운로드하는 데 필요한 시간을 계산합니다. 결과가 캐시에 저장되기 때문에 다운로드 작업의 두 번째 집합은 첫 번째 집합보다 시간이 덜 걸려야 합니다. <xref:System.Threading.Tasks.Task.FromResult%2A> 메서드는 `DownloadStringAsync` 메서드가 이러한 미리 계산된 결과를 포함하는 <xref:System.Threading.Tasks.Task%601> 개체를 만들 수 있도록 합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나, `CachedDownloads.cs`(Visual Basic의 경우 `CachedDownloads.vb`) 파일에 붙여넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 Visual C#  
  
 **csc.exe CachedDownloads.cs**  
  
 Visual Basic  
  
 **vbc.exe CachedDownloads.vb**  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
  
## <a name="see-also"></a>참고 항목  
 [작업 기반 비동기 프로그래밍](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
