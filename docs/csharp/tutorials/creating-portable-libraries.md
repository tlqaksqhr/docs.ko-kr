---
title: "이식 가능한 라이브러리 만들기 - C# 가이드"
description: "이식 가능한 라이브러리를 만들고 라이브러리가 지원하는 플랫폼 및 버전을 지정하는 방법을 알아봅니다."
keywords: "C#, UWP, 이식 가능한 어셈블리, 플랫폼 간"
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 254836c0-3be7-4549-bd9a-40fc0f445c31
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 534380026773fb2e2203db502b21b8c0ac3d3081
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="creating-portable-libraries"></a><span data-ttu-id="a7927-104">이식 가능한 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="a7927-104">Creating Portable Libraries</span></span>

> <span data-ttu-id="a7927-105">**참고:**</span><span class="sxs-lookup"><span data-stu-id="a7927-105">**Note**</span></span>
> 
> <span data-ttu-id="a7927-106">이 항목은 아직 작성되지 않았습니다!</span><span class="sxs-lookup"><span data-stu-id="a7927-106">This topic hasn't been written yet!</span></span> 
>
> <span data-ttu-id="a7927-107">범위와 방법을 구성하는 데 도움이 될 의견을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="a7927-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="a7927-108">GitHub에서 상태를 추적하고 이 [문제](https://github.com/dotnet/docs/issues/950)에 대한 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7927-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/950) at GitHub.</span></span>
> 
> <span data-ttu-id="a7927-109">이 항목의 초기 초안 및 개요를 검토하려면 문제에서 연락처 정보가 포함된 메모를 남겨 주세요.</span><span class="sxs-lookup"><span data-stu-id="a7927-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="a7927-110">[GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)에 기여할 수 있는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a7927-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

