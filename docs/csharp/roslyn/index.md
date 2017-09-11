---
title: ".NET 컴파일러 SDK 사용 - C# 가이드"
description: "Roslyn API를 탐색하여 자동 진단 및 코드 수정 만들기"
keywords: .NET, .NET Core, C#, Roslyn,
ms.date: 06/25/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: abed9e00-2ddc-468e-9cca-d033bd6a7e36
redirect_url: /dotnet/csharp/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b227d67fd5431da328e1686fd9afc6a3b9db035e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="-using-the-net-compiler-sdk"></a><span data-ttu-id="bc6dd-104">🔧 .NET 컴파일러 플랫폼 사용</span><span class="sxs-lookup"><span data-stu-id="bc6dd-104">🔧 Using the .NET Compiler SDK</span></span>

> <span data-ttu-id="bc6dd-105">**참고:**</span><span class="sxs-lookup"><span data-stu-id="bc6dd-105">**Note**</span></span>
> 
> <span data-ttu-id="bc6dd-106">이 항목은 아직 작성되지 않았습니다!</span><span class="sxs-lookup"><span data-stu-id="bc6dd-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="bc6dd-107">범위와 방법을 구성하는 데 도움이 될 의견을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="bc6dd-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="bc6dd-108">GitHub에서 상태를 추적하고 이 [문제](https://github.com/dotnet/docs/issues/972)에 대한 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc6dd-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/972) at GitHub.</span></span>
> 
> <span data-ttu-id="bc6dd-109">이 항목의 초기 초안 및 개요를 검토하려면 문제에서 연락처 정보가 포함된 메모를 남겨 주세요.</span><span class="sxs-lookup"><span data-stu-id="bc6dd-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="bc6dd-110">[GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)에 기여할 수 있는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="bc6dd-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

<span data-ttu-id="bc6dd-111">이 항목은 전체 섹션에 대한 메타 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="bc6dd-111">This is a meta-topic for an entire section.</span></span> <span data-ttu-id="bc6dd-112">여기에서 다루어져야 하는 영역에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc6dd-112">Areas that need to be covered here include:</span></span> 
* <span data-ttu-id="bc6dd-113">시작</span><span class="sxs-lookup"><span data-stu-id="bc6dd-113">Getting Started</span></span>
* <span data-ttu-id="bc6dd-114">샘플 및 자습서</span><span class="sxs-lookup"><span data-stu-id="bc6dd-114">Samples and tutorials</span></span>
* <span data-ttu-id="bc6dd-115">개념 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="bc6dd-115">conceptual content</span></span>
* <span data-ttu-id="bc6dd-116">API의 전체 모델</span><span class="sxs-lookup"><span data-stu-id="bc6dd-116">overall model of the APIs</span></span>
* <span data-ttu-id="bc6dd-117">[roslyn-analyzers](http://github.com/dotnet/roslyn-analyzers) 리포지토리의 샘플로 연결되는 링크</span><span class="sxs-lookup"><span data-stu-id="bc6dd-117">links to samples on the [roslyn-analyzers](http://github.com/dotnet/roslyn-analyzers) repository</span></span>
* <span data-ttu-id="bc6dd-118">다른 참조 내용에 대한 링크</span><span class="sxs-lookup"><span data-stu-id="bc6dd-118">links to other reference content</span></span>

