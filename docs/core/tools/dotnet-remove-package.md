---
title: dotnet remove package 명령 - .NET Core CLI
description: dotnet remove package 명령은 프로젝트에 대한 NuGet 패키지 참조를 제거하는 편리한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ed6086bfdfadaa06494c857fc74687f1273af971
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696860"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="f1608-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="f1608-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f1608-104">name</span><span class="sxs-lookup"><span data-stu-id="f1608-104">Name</span></span>

<span data-ttu-id="f1608-105">`dotnet remove package` - 프로젝트 파일에서 패키지 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f1608-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f1608-106">개요</span><span class="sxs-lookup"><span data-stu-id="f1608-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="f1608-107">설명</span><span class="sxs-lookup"><span data-stu-id="f1608-107">Description</span></span>

<span data-ttu-id="f1608-108">`dotnet remove package` 명령은 프로젝트에서 NuGet 패키지 참조를 제거하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1608-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="f1608-109">인수</span><span class="sxs-lookup"><span data-stu-id="f1608-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="f1608-110">프로젝트 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1608-110">Specifies the project file.</span></span> <span data-ttu-id="f1608-111">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f1608-111">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="f1608-112">제거할 패키지 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="f1608-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="f1608-113">옵션</span><span class="sxs-lookup"><span data-stu-id="f1608-113">Options</span></span>

`-h|--help`

<span data-ttu-id="f1608-114">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f1608-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="f1608-115">예제</span><span class="sxs-lookup"><span data-stu-id="f1608-115">Examples</span></span>

<span data-ttu-id="f1608-116">현재 디렉터리의 프로젝트에서 `Newtonsoft.Json` NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f1608-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`