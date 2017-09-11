---
title: "global.json 참조"
description: ".NET Core 도구 버전 설정을 허용하는 global.json 파일의 스키마를 참조하세요."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffa97164736fc7f3edc450682d23bdf499b6eb34
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="globaljson-reference"></a><span data-ttu-id="e5704-104">global.json 참조</span><span class="sxs-lookup"><span data-stu-id="e5704-104">global.json reference</span></span>

<span data-ttu-id="e5704-105">*global.json* 파일을 사용하면 `sdk` 속성을 통해 사용 중인 .NET Core 도구 버전을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5704-105">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="e5704-106">.NET Core CLI 도구는 현재 작업 디렉터리(프로젝트 디렉터리와 다를 수 있음) 또는 해당 부모 디렉터리 중 하나에서 이 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e5704-106">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="e5704-107">sdk</span><span class="sxs-lookup"><span data-stu-id="e5704-107">sdk</span></span>
<span data-ttu-id="e5704-108">형식: Object</span><span class="sxs-lookup"><span data-stu-id="e5704-108">Type: Object</span></span>

<span data-ttu-id="e5704-109">SDK에 대한 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5704-109">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="e5704-110">version</span><span class="sxs-lookup"><span data-stu-id="e5704-110">version</span></span>
<span data-ttu-id="e5704-111">형식: String</span><span class="sxs-lookup"><span data-stu-id="e5704-111">Type: String</span></span>

<span data-ttu-id="e5704-112">사용할 SDK의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e5704-112">The version of the SDK to use.</span></span>

<span data-ttu-id="e5704-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5704-113">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```

