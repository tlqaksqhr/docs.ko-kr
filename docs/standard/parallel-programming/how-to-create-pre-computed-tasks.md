---
title: '방법: 미리 계산된 작업 만들기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5d688041c6a8947b4a30f067d969cb6cb3bbf0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583905"
---
# <a name="how-to-create-pre-computed-tasks"></a><span data-ttu-id="b8520-102">방법: 미리 계산된 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="b8520-102">How to: Create Pre-Computed Tasks</span></span>
<span data-ttu-id="b8520-103">이 문서에서는 <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> 메서드를 사용하여 캐시에 저장된 비동기 다운로드 작업의 결과를 검색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-103">This document describes how to use the <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> method to retrieve the results of asynchronous download operations that are held in a cache.</span></span> <span data-ttu-id="b8520-104"><xref:System.Threading.Tasks.Task.FromResult%2A> 메서드는 제공된 값을 <xref:System.Threading.Tasks.Task%601> 속성으로 포함하는 완료된 <xref:System.Threading.Tasks.Task%601.Result%2A> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-104">The <xref:System.Threading.Tasks.Task.FromResult%2A> method returns a finished <xref:System.Threading.Tasks.Task%601> object that holds the provided value as its <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="b8520-105">이 메서드는 <xref:System.Threading.Tasks.Task%601> 개체가 반환되는 비동기 작업을 수행하고 해당 <xref:System.Threading.Tasks.Task%601> 개체의 결과가 계산되어 있을 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-105">This method is useful when you perform an asynchronous operation that returns a <xref:System.Threading.Tasks.Task%601> object, and the result of that <xref:System.Threading.Tasks.Task%601> object is already computed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8520-106">예</span><span class="sxs-lookup"><span data-stu-id="b8520-106">Example</span></span>  
 <span data-ttu-id="b8520-107">다음 예제에서는 웹에서 문자열을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-107">The following example downloads strings from the web.</span></span> <span data-ttu-id="b8520-108">이 예제에서는 `DownloadStringAsync` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-108">It defines the `DownloadStringAsync` method.</span></span> <span data-ttu-id="b8520-109">이 메서드는 웹에서 문자열을 비동기적으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-109">This method downloads strings from the web asynchronously.</span></span> <span data-ttu-id="b8520-110">또한 이 예제에서는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>개체를 사용하여 이전 작업의 결과를 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-110">This example also uses a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> object to cache the results of previous operations.</span></span> <span data-ttu-id="b8520-111">입력 주소가 이 캐시에 저장된 경우 `DownloadStringAsync`는 <xref:System.Threading.Tasks.Task.FromResult%2A> 메서드를 사용하여 해당 주소의 콘텐츠를 포함하는 <xref:System.Threading.Tasks.Task%601> 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-111">If the input address is held in this cache, `DownloadStringAsync` uses the <xref:System.Threading.Tasks.Task.FromResult%2A> method to produce a <xref:System.Threading.Tasks.Task%601> object that holds the content at that address.</span></span> <span data-ttu-id="b8520-112">그렇지 않은 경우에는 `DownloadStringAsync`가 웹에서 파일을 다운로드하고 결과를 캐시에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-112">Otherwise, `DownloadStringAsync` downloads the file from the web and adds the result to the cache.</span></span>  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 <span data-ttu-id="b8520-113">이 예제에서는 여러 문자열을 두 번 다운로드하는 데 필요한 시간을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-113">This example computes the time that is required to download multiple strings two times.</span></span> <span data-ttu-id="b8520-114">결과가 캐시에 저장되기 때문에 다운로드 작업의 두 번째 집합은 첫 번째 집합보다 시간이 덜 걸려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-114">The second set of download operations should take less time than the first set because the results are held in the cache.</span></span> <span data-ttu-id="b8520-115"><xref:System.Threading.Tasks.Task.FromResult%2A> 메서드는 `DownloadStringAsync` 메서드가 이러한 미리 계산된 결과를 포함하는 <xref:System.Threading.Tasks.Task%601> 개체를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-115">The <xref:System.Threading.Tasks.Task.FromResult%2A> method enables the `DownloadStringAsync` method to create <xref:System.Threading.Tasks.Task%601> objects that hold these pre-computed results.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b8520-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b8520-116">Compiling the Code</span></span>  
 <span data-ttu-id="b8520-117">예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나, `CachedDownloads.cs`(Visual Basic의 경우 `CachedDownloads.vb`) 파일에 붙여넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b8520-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `CachedDownloads.cs` (`CachedDownloads.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="b8520-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="b8520-118">Visual C#</span></span>  
  
 <span data-ttu-id="b8520-119">**csc.exe CachedDownloads.cs**</span><span class="sxs-lookup"><span data-stu-id="b8520-119">**csc.exe CachedDownloads.cs**</span></span>  
  
 <span data-ttu-id="b8520-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8520-120">Visual Basic</span></span>  
  
 <span data-ttu-id="b8520-121">**vbc.exe CachedDownloads.vb**</span><span class="sxs-lookup"><span data-stu-id="b8520-121">**vbc.exe CachedDownloads.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b8520-122">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b8520-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8520-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8520-123">See Also</span></span>  
 [<span data-ttu-id="b8520-124">작업 기반 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b8520-124">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
