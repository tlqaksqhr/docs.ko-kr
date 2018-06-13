---
title: 앱 설정 스키마
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 154f38880225fb420f9944f336ff885bd116e2c3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743773"
---
# <a name="app-settings-schema"></a><span data-ttu-id="3d6ef-102">앱 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3d6ef-102">App Settings schema</span></span>

<span data-ttu-id="3d6ef-103">파일 경로, XML Web services URL 또는 응용 프로그램의 기타 사용자 지정 구성 정보와 같은 사용자 지정 응용 프로그램 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="3d6ef-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="3d6ef-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="3d6ef-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="3d6ef-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="3d6ef-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="3d6ef-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) </span></span>  
<span data-ttu-id="3d6ef-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="3d6ef-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) </span></span>  
<span data-ttu-id="3d6ef-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="3d6ef-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="3d6ef-109">요소</span><span class="sxs-lookup"><span data-stu-id="3d6ef-109">Element</span></span> | <span data-ttu-id="3d6ef-110">설명</span><span class="sxs-lookup"><span data-stu-id="3d6ef-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="3d6ef-111">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="3d6ef-111">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="3d6ef-112">응용 프로그램 설정을 제어하기 위한 **\<add>**, **\<clear>** 및 **\<remove>** 태그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="3d6ef-113">선택적 **파일** 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="3d6ef-114">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="3d6ef-114">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="3d6ef-115">설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-115">Defines a setting.</span></span> <span data-ttu-id="3d6ef-116">**\<appSettings>** 의 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="3d6ef-117">**키** 및 **값** 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="3d6ef-118">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="3d6ef-118">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="3d6ef-119">모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-119">Clears all settings.</span></span> <span data-ttu-id="3d6ef-120">**\<appSettings>** 의 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="3d6ef-121">특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-121">Has no attributes.</span></span> |
| [<span data-ttu-id="3d6ef-122">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="3d6ef-122">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="3d6ef-123">설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-123">Removes a setting.</span></span> <span data-ttu-id="3d6ef-124">**\<appSettings>** 의 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="3d6ef-125">**키** 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="3d6ef-126">\<appSettings> 요소</span><span class="sxs-lookup"><span data-stu-id="3d6ef-126">\<appSettings> element</span></span>

<span data-ttu-id="3d6ef-127">이 요소에는 응용 프로그램 설정을 제어하기 위한 **\<add>**, **\<clear>** 및 **\<remove>** 태그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="3d6ef-128">**파일**에 대한 선택적 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="3d6ef-129">\<add> 요소</span><span class="sxs-lookup"><span data-stu-id="3d6ef-129">\<add> element</span></span>

<span data-ttu-id="3d6ef-130">응용 프로그램 설정 컬렉션에 사용자 지정 응용 프로그램 설정을 이름/값 쌍으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="3d6ef-131">**키** 및 **값**에 대한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="3d6ef-132">\<clear> 요소</span><span class="sxs-lookup"><span data-stu-id="3d6ef-132">\<clear> element</span></span>

<span data-ttu-id="3d6ef-133">상속된 사용자 지정 응용 프로그램 설정에 대한 참조를 모두 제거하고, **\<clear>** 요소 다음의 **\<add>** 요소에 의해 추가된 참조만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="3d6ef-134">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="3d6ef-135">\<remove> 요소</span><span class="sxs-lookup"><span data-stu-id="3d6ef-135">\<remove> element</span></span>

<span data-ttu-id="3d6ef-136">상속된 사용자 지정 응용 프로그램 설정에 대한 참조를 응용 프로그램 설정 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="3d6ef-137">**키**에 대한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="3d6ef-138">예제</span><span class="sxs-lookup"><span data-stu-id="3d6ef-138">Example</span></span>

<span data-ttu-id="3d6ef-139">다음 예제에서는 사용자 지정 응용 프로그램 설정을 정의하는 외부 응용 프로그램 설정 파일(*custom.config*)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="3d6ef-140">다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 응용 프로그램 설정을 지정하는 응용 프로그램 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d6ef-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="3d6ef-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="3d6ef-141">See also</span></span>

<span data-ttu-id="3d6ef-142">[응용 프로그램 설정 개요](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="3d6ef-142">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="3d6ef-143">응용 프로그램 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="3d6ef-143">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
