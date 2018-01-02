---
title: "앱 설정 스키마"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 028fdbeb90a1499459803f24f3aa62923452edba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="app-settings-schema"></a><span data-ttu-id="707a5-102">앱 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="707a5-102">App Settings schema</span></span>

<span data-ttu-id="707a5-103">파일 경로, XML Web services URL 또는 응용 프로그램의 기타 사용자 지정 구성 정보와 같은 사용자 지정 응용 프로그램 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="707a5-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="707a5-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="707a5-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="707a5-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="707a5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="707a5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span></span>  
<span data-ttu-id="707a5-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="707a5-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span></span>  
<span data-ttu-id="707a5-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="707a5-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="707a5-109">요소</span><span class="sxs-lookup"><span data-stu-id="707a5-109">Element</span></span> | <span data-ttu-id="707a5-110">설명</span><span class="sxs-lookup"><span data-stu-id="707a5-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="707a5-111">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="707a5-111">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="707a5-112">응용 프로그램 설정을 제어하기 위한 **\<add>**, **\<clear>** 및 **\<remove>** 태그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="707a5-113">선택적 **파일** 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="707a5-114">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="707a5-114">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="707a5-115">설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-115">Defines a setting.</span></span> <span data-ttu-id="707a5-116">**\<appSettings>**의 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="707a5-117">**키** 및 **값** 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="707a5-118">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="707a5-118">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="707a5-119">모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-119">Clears all settings.</span></span> <span data-ttu-id="707a5-120">**\<appSettings>**의 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="707a5-121">특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-121">Has no attributes.</span></span> |
| [<span data-ttu-id="707a5-122">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="707a5-122">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="707a5-123">설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-123">Removes a setting.</span></span> <span data-ttu-id="707a5-124">**\<appSettings>**의 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="707a5-125">**키** 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="707a5-126">\<appSettings> 요소</span><span class="sxs-lookup"><span data-stu-id="707a5-126">\<appSettings> element</span></span>

<span data-ttu-id="707a5-127">이 요소에는 응용 프로그램 설정을 제어하기 위한 **\<add>**, **\<clear>** 및 **\<remove>** 태그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="707a5-128">**파일**에 대한 선택적 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="707a5-129">\<add> 요소</span><span class="sxs-lookup"><span data-stu-id="707a5-129">\<add> element</span></span>

<span data-ttu-id="707a5-130">응용 프로그램 설정 컬렉션에 사용자 지정 응용 프로그램 설정을 이름/값 쌍으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="707a5-131">**키** 및 **값**에 대한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="707a5-132">\<clear> 요소</span><span class="sxs-lookup"><span data-stu-id="707a5-132">\<clear> element</span></span>

<span data-ttu-id="707a5-133">상속된 사용자 지정 응용 프로그램 설정에 대한 참조를 모두 제거하고, **\<clear>** 요소 다음의 **\<add>** 요소에 의해 추가된 참조만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="707a5-134">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="707a5-135">\<remove> 요소</span><span class="sxs-lookup"><span data-stu-id="707a5-135">\<remove> element</span></span>

<span data-ttu-id="707a5-136">상속된 사용자 지정 응용 프로그램 설정에 대한 참조를 응용 프로그램 설정 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="707a5-137">**키**에 대한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="707a5-138">예</span><span class="sxs-lookup"><span data-stu-id="707a5-138">Example</span></span>

<span data-ttu-id="707a5-139">다음 예제에서는 사용자 지정 응용 프로그램 설정을 정의하는 외부 응용 프로그램 설정 파일(*custom.config*)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="707a5-140">다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 응용 프로그램 설정을 지정하는 응용 프로그램 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="707a5-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="707a5-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="707a5-141">See also</span></span>

<span data-ttu-id="707a5-142">[응용 프로그램 설정 개요](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="707a5-142">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="707a5-143">응용 프로그램 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="707a5-143">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
