---
title: "비동기 UI 프로그래밍 - C# 가이드"
description: "비동기 작업에 대한 프로그래밍이 수행되는 동안 UI가 응답하도록 하는 기술 알아보기"
keywords: C#, UWP, XAML
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7402b29b-1093-456d-be4c-f60ecb8926bb
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f868c798f94acfb1ef468ea91f4245520c4e14b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="-asynchronous-ui-programming"></a><span data-ttu-id="14823-104">🔧 비동기 UI 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="14823-104">🔧 Asynchronous UI Programming</span></span>

> <span data-ttu-id="14823-105">**참고:**</span><span class="sxs-lookup"><span data-stu-id="14823-105">**Note**</span></span>
> 
> <span data-ttu-id="14823-106">이 항목은 아직 작성되지 않았습니다!</span><span class="sxs-lookup"><span data-stu-id="14823-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="14823-107">범위와 방법을 구성하는 데 도움이 될 의견을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="14823-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="14823-108">GitHub에서 상태를 추적하고 이 [문제](https://github.com/dotnet/docs/issues/951)에 대한 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14823-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/951) at GitHub.</span></span>
> 
> <span data-ttu-id="14823-109">이 항목의 초기 초안 및 개요를 검토하려면 문제에서 연락처 정보가 포함된 메모를 남겨 주세요.</span><span class="sxs-lookup"><span data-stu-id="14823-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="14823-110">[GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)에 기여할 수 있는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="14823-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

