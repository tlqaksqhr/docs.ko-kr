---
title: 'F # 시작'
description: 'F # 언어.net에서 프로그래밍을 시작 하는 방법을 알아봅니다.'
keywords: visual f#, f#, 함수형 프로그래밍, .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 09/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: 34e476054e8dbc6c41f3e9cee733e094a5f4e24e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="getting-started-with-f"></a><span data-ttu-id="70e55-104">F # 시작</span><span class="sxs-lookup"><span data-stu-id="70e55-104">Getting Started with F#</span></span> #

<span data-ttu-id="70e55-105">F #을 시작 하는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e55-105">There are multiple ways to get started with F#.</span></span>  <span data-ttu-id="70e55-106">여러 아티클을 각 주요 방법에 대 한 한 지침을 제공 하도록 기록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="70e55-106">We have multiple articles written to provide a guide for each major way.</span></span>  <span data-ttu-id="70e55-107">다음 표에서 의사 결정을 내리는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e55-107">You can use the following table to help in making a decision.</span></span>

| <span data-ttu-id="70e55-108">운영 체제</span><span class="sxs-lookup"><span data-stu-id="70e55-108">OS</span></span> | <span data-ttu-id="70e55-109">Visual Studio를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e55-109">Prefer Visual Studio</span></span> | <span data-ttu-id="70e55-110">Visual Studio Code를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e55-110">Prefer Visual Studio Code</span></span> | <span data-ttu-id="70e55-111">명령줄을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e55-111">Prefer a command line</span></span> |
| -- |------------------------|--------------------------|-----------------------------|-------------------------|
| <span data-ttu-id="70e55-112">Windows</span><span class="sxs-lookup"><span data-stu-id="70e55-112">Windows</span></span> | [<span data-ttu-id="70e55-113">Visual Studio 시작</span><span class="sxs-lookup"><span data-stu-id="70e55-113">Get started with Visual Studio</span></span>](get-started-visual-studio.md) | [<span data-ttu-id="70e55-114">VSCode 및 Ionide 시작</span><span class="sxs-lookup"><span data-stu-id="70e55-114">Get started with VSCode and Ionide</span></span>](get-started-vscode.md) | [<span data-ttu-id="70e55-115">.NET Core CLI 시작</span><span class="sxs-lookup"><span data-stu-id="70e55-115">Get started with the .NET Core CLI</span></span>](get-started-command-line.md) |
| <span data-ttu-id="70e55-116">MacOS</span><span class="sxs-lookup"><span data-stu-id="70e55-116">macOS</span></span> | [<span data-ttu-id="70e55-117">Mac 용 VS 시작</span><span class="sxs-lookup"><span data-stu-id="70e55-117">Get started with VS for Mac</span></span>](get-started-with-visual-studio-for-mac.md) | [<span data-ttu-id="70e55-118">VSCode 및 Ionide 시작</span><span class="sxs-lookup"><span data-stu-id="70e55-118">Get started with VSCode and Ionide</span></span>](get-started-vscode.md) | [<span data-ttu-id="70e55-119">.NET Core CLI 시작</span><span class="sxs-lookup"><span data-stu-id="70e55-119">Get started with the .NET Core CLI</span></span>](get-started-command-line.md) |
| <span data-ttu-id="70e55-120">Linux</span><span class="sxs-lookup"><span data-stu-id="70e55-120">Linux</span></span> | <span data-ttu-id="70e55-121">N/A</span><span class="sxs-lookup"><span data-stu-id="70e55-121">N/A</span></span> | [<span data-ttu-id="70e55-122">VSCode 및 Ionide 시작</span><span class="sxs-lookup"><span data-stu-id="70e55-122">Get started with VSCode and Ionide</span></span>](get-started-vscode.md) | [<span data-ttu-id="70e55-123">.NET Core CLI 시작</span><span class="sxs-lookup"><span data-stu-id="70e55-123">Get started with the .NET Core CLI</span></span>](get-started-command-line.md) |

<span data-ttu-id="70e55-124">일반적으로 특정 방법이 있으면 시작 하려면 나머지 보다 좋은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70e55-124">In general, there is no specific way to get started which is better than the rest.</span></span>  <span data-ttu-id="70e55-125">F #을 사용 하 여 컴퓨터에 어떤 점이 좋은지 참조 하는 모든 방법을 시도 하는 것이 좋습니다 최고!</span><span class="sxs-lookup"><span data-stu-id="70e55-125">We recommend trying all ways to use F# on your machine to see what you like the best!</span></span>
