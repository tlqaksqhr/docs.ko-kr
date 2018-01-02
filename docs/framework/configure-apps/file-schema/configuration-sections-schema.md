---
title: "구성 섹션 스키마"
ms.date: 05/02/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da9af8fd24f1bf6e6effd411ad37490a4ee08804
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="e1273-102">구성 섹션 스키마</span><span class="sxs-lookup"><span data-stu-id="e1273-102">Configuration sections schema</span></span>

<span data-ttu-id="e1273-103">구성 섹션 스키마 구성 파일에서 사용자 지정 설정을 정의 하는 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1273-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="e1273-104">구성 파일 및 스키마에 대 한 일반적인 정보를 참조 하십시오. [.NET Framework에 대 한 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1273-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="e1273-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e1273-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="e1273-106">[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e1273-106">[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="e1273-107">[**\<지우기 >**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="e1273-107">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="e1273-108">[**\<제거 >**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="e1273-108">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="e1273-109">[**\<섹션 >**](~/docs/framework/configure-apps/file-schema/section-element.md) </span><span class="sxs-lookup"><span data-stu-id="e1273-109">[**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) </span></span>  
[<span data-ttu-id="e1273-110">**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="e1273-110">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="e1273-111">설명</span><span class="sxs-lookup"><span data-stu-id="e1273-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e1273-112">**\<지우기 >** 에 대 한  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="e1273-112">**\<clear>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="e1273-113">이전에 정의 된 모든 섹션과 섹션 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e1273-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="e1273-114">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="e1273-114">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="e1273-115">이전에 정의 된 모든 섹션과 섹션 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e1273-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="e1273-116">**\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="e1273-116">**\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="e1273-117">구성 섹션 및 네임 스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e1273-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="e1273-118">**\<제거 >** 에 대 한  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="e1273-118">**\<remove>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="e1273-119">미리 정의 된 섹션 또는 섹션 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e1273-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="e1273-120">**\<섹션 >** 에 대 한  **\<configSections >** 및  **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="e1273-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="e1273-121">구성 섹션 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e1273-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="e1273-122">**\<sectionGroup >** 에 대 한  **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="e1273-122">**\<sectionGroup>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="e1273-123">구성 섹션에 대 한 네임 스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e1273-123">Defines a namespace for configuration sections.</span></span> |
