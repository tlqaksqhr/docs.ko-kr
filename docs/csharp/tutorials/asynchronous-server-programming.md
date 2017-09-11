---
title: "비동기 서버 프로그래밍 - C# 가이드"
description: "비동기 프로그래밍 기법을 사용하여 서버 작업을 오프로드하기 위한 기술 알아보기"
keywords: "C#, 비동기, CPU 바인딩, 네트워크 바인딩"
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7402b29b-1093-456d-be4c-f60ecb8926bb
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 390d0eb2c8416165984ffe6c80ed6977e61a2845
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="-asynchronous-server-programming"></a><span data-ttu-id="fd012-104">🔧 비동기 서버 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fd012-104">🔧 Asynchronous Server Programming</span></span>

> <span data-ttu-id="fd012-105">**참고:**</span><span class="sxs-lookup"><span data-stu-id="fd012-105">**Note**</span></span>
> 
> <span data-ttu-id="fd012-106">이 항목은 아직 작성되지 않았습니다!</span><span class="sxs-lookup"><span data-stu-id="fd012-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="fd012-107">범위와 방법을 구성하는 데 도움이 될 의견을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="fd012-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="fd012-108">GitHub에서 상태를 추적하고 이 [문제](https://github.com/dotnet/docs/issues/952)에 대한 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd012-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/952) at GitHub.</span></span>
> 
> <span data-ttu-id="fd012-109">이 항목의 초기 초안 및 개요를 검토하려면 문제에서 연락처 정보가 포함된 메모를 남겨 주세요.</span><span class="sxs-lookup"><span data-stu-id="fd012-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="fd012-110">[GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)에 기여할 수 있는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="fd012-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

