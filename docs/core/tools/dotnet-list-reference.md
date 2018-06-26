---
title: dotnet list reference 명령 - .NET Core CLI
description: dotnet list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 821e6d276af44bf984c8ac1b42b4e954dbe69556
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697185"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="8d956-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="8d956-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="8d956-104">name</span><span class="sxs-lookup"><span data-stu-id="8d956-104">Name</span></span>

<span data-ttu-id="8d956-105">`dotnet list reference` - 프로젝트 간 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8d956-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8d956-106">개요</span><span class="sxs-lookup"><span data-stu-id="8d956-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="8d956-107">설명</span><span class="sxs-lookup"><span data-stu-id="8d956-107">Description</span></span>

<span data-ttu-id="8d956-108">`dotnet list reference` 명령은 지정한 프로젝트에 대해 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d956-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="8d956-109">인수</span><span class="sxs-lookup"><span data-stu-id="8d956-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="8d956-110">참조를 나열하기 위해 사용할 프로젝트 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d956-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="8d956-111">지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8d956-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="8d956-112">옵션</span><span class="sxs-lookup"><span data-stu-id="8d956-112">Options</span></span>

`-h|--help`

<span data-ttu-id="8d956-113">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8d956-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="8d956-114">예제</span><span class="sxs-lookup"><span data-stu-id="8d956-114">Examples</span></span>

<span data-ttu-id="8d956-115">지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8d956-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="8d956-116">현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8d956-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`