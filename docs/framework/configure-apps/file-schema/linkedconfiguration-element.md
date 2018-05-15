---
title: '&lt;linkedConfiguration&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 71769efa1233fc8a693219dc02ae56ea39c164e7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="276c1-102">\<linkedConfiguration > 요소</span><span class="sxs-lookup"><span data-stu-id="276c1-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="276c1-103">포함할 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="276c1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="276c1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="276c1-105">&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="276c1-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="276c1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="276c1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="276c1-107">구문</span><span class="sxs-lookup"><span data-stu-id="276c1-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="276c1-108">특성</span><span class="sxs-lookup"><span data-stu-id="276c1-108">Attribute</span></span>

|           | <span data-ttu-id="276c1-109">설명</span><span class="sxs-lookup"><span data-stu-id="276c1-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="276c1-110">**href**</span><span class="sxs-lookup"><span data-stu-id="276c1-110">**href**</span></span>  | <span data-ttu-id="276c1-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-111">Required attribute.</span></span><br><br><span data-ttu-id="276c1-112">포함할 구성 파일의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="276c1-113">에 대 한 지원 되는 유일한 형식은 **href** 특성은 `file://`합니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="276c1-114">로컬 파일과 UNC 파일 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="276c1-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="276c1-115">Parent element</span></span>

|     | <span data-ttu-id="276c1-116">설명</span><span class="sxs-lookup"><span data-stu-id="276c1-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="276c1-117">**\<assemblyBinding >** 요소</span><span class="sxs-lookup"><span data-stu-id="276c1-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="276c1-118">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="276c1-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="276c1-119">Child elements</span></span>

<span data-ttu-id="276c1-120">없음</span><span class="sxs-lookup"><span data-stu-id="276c1-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="276c1-121">설명</span><span class="sxs-lookup"><span data-stu-id="276c1-121">Remarks</span></span>

<span data-ttu-id="276c1-122">**\<linkedConfiguration >** 요소 구성 요소 어셈블리에 대 한 서비스를 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="276c1-123">어셈블리를 사용 하는 응용 프로그램의 구성 파일 하나 이상의 응용 프로그램에서 잘 알려진 위치에 있는 구성 파일을 포함 하는 어셈블리를 사용 하는 경우 사용할 수는  **\<linkedConfiguration >** 직접 구성 정보를 포함 하는 것 보다는 어셈블리 구성 파일을 포함 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="276c1-124">구성 요소 어셈블리를 서비스를 제공 하는 경우 어셈블리를 사용 하는 모든 응용 프로그램에 업데이트 된 구성 정보를 제공 일반적인 구성 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="276c1-125">**\<linkedConfiguration >** Windows-side-by-side 매니페스트도 응용 프로그램에 대 한 요소가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="276c1-126">연결 된 구성 파일의 사용을 통제 하는 다음 규칙:</span><span class="sxs-lookup"><span data-stu-id="276c1-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="276c1-127">만 포함 된 구성 파일에서 설정을 로더 바인딩 정책에 영향을 하 게 되 고 로더에 의해서만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="276c1-128">포함 된 구성 파일에는 바인딩 정책 이외의 설정이 있을 수 있지만 해당 설정에 영향을 줄 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="276c1-129">에 대 한 지원 되는 유일한 형식은 `href` 특성은 `file://`합니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="276c1-130">로컬 파일과 UNC 파일 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="276c1-131">각 구성 파일에 연결 된 구성 수에 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="276c1-132">모든 연결 된 구성 파일의 동작과 비슷하지만 한 파일로 병합 됩니다는 `#include` C/c + +에서 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="276c1-133">**\<linkedConfiguration >** 요소를 응용 프로그램 구성 파일에만 사용할 수 있습니다.;에서 무시 됩니다 *Machine.config*합니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="276c1-134">순환 참조를 감지 하 여 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="276c1-135">즉, 하는 경우는  **\<linkedConfiguration >** 루프를 형성 하는 일련의 구성 파일의 요소, 루프 감지 되 고 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="276c1-136">예제</span><span class="sxs-lookup"><span data-stu-id="276c1-136">Example</span></span>

<span data-ttu-id="276c1-137">다음 예제에는 로컬 하드 디스크에서 구성 파일을 포함 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="276c1-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="276c1-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="276c1-138">See also</span></span>

<span data-ttu-id="276c1-139">[**\<assemblyBinding >** 요소](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="276c1-139">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
[<span data-ttu-id="276c1-140">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="276c1-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
