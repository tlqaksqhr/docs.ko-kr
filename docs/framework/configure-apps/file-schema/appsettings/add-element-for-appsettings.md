---
title: '&lt;추가&gt; 요소에 대 한 &lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 35a9fc08033d2b9cd1dae5a1f1f3ddcd361f03eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753640"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="119e9-102">\<추가 > 요소에 대 한 \<g s ></span><span class="sxs-lookup"><span data-stu-id="119e9-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="119e9-103">사용자 지정 응용 프로그램 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="119e9-103">Adds a custom application setting.</span></span>

<span data-ttu-id="119e9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="119e9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="119e9-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="119e9-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="119e9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<추가 >**</span><span class="sxs-lookup"><span data-stu-id="119e9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="119e9-107">구문</span><span class="sxs-lookup"><span data-stu-id="119e9-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="119e9-108">특성</span><span class="sxs-lookup"><span data-stu-id="119e9-108">Attributes</span></span>

|           | <span data-ttu-id="119e9-109">설명</span><span class="sxs-lookup"><span data-stu-id="119e9-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="119e9-110">**key**</span><span class="sxs-lookup"><span data-stu-id="119e9-110">**key**</span></span>   | <span data-ttu-id="119e9-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="119e9-111">Required attribute.</span></span><br><br><span data-ttu-id="119e9-112">추가할 키의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="119e9-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="119e9-113">**value**</span><span class="sxs-lookup"><span data-stu-id="119e9-113">**value**</span></span> | <span data-ttu-id="119e9-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="119e9-114">Required attribute.</span></span><br><br><span data-ttu-id="119e9-115">추가할 키의 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="119e9-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="119e9-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="119e9-116">Parent element</span></span>

|     | <span data-ttu-id="119e9-117">설명</span><span class="sxs-lookup"><span data-stu-id="119e9-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="119e9-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="119e9-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="119e9-119">파일 경로, XML Web services URL 또는 응용 프로그램의 기타 사용자 지정 구성 정보와 같은 사용자 지정 응용 프로그램 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="119e9-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="119e9-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="119e9-120">Child elements</span></span>

<span data-ttu-id="119e9-121">없음</span><span class="sxs-lookup"><span data-stu-id="119e9-121">None</span></span>

## <a name="example"></a><span data-ttu-id="119e9-122">예제</span><span class="sxs-lookup"><span data-stu-id="119e9-122">Example</span></span>

<span data-ttu-id="119e9-123">다음 예제에서는 응용 프로그램의 이름에 대 한 사용자 지정 구성 설정을 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="119e9-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="119e9-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="119e9-124">See also</span></span>

[<span data-ttu-id="119e9-125">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="119e9-125">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
