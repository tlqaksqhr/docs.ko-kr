---
title: '&lt;appSettings&gt; 요소에 대 한 &lt;구성&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d17400536b911ce0be4d2bf105b0b4d99d0916df
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="b5725-102">\<g s > 요소에 대 한 \<구성 ></span><span class="sxs-lookup"><span data-stu-id="b5725-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="b5725-103">사용자 지정 응용 프로그램 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-103">Contains custom application settings.</span></span> <span data-ttu-id="b5725-104">.NET Framework에서 제공 하는 미리 정의 된 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="b5725-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b5725-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="b5725-106">&nbsp;&nbsp;**\<g s >**</span><span class="sxs-lookup"><span data-stu-id="b5725-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b5725-107">구문</span><span class="sxs-lookup"><span data-stu-id="b5725-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="b5725-108">특성</span><span class="sxs-lookup"><span data-stu-id="b5725-108">Attribute</span></span>

|           | <span data-ttu-id="b5725-109">설명</span><span class="sxs-lookup"><span data-stu-id="b5725-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b5725-110">**file**</span><span class="sxs-lookup"><span data-stu-id="b5725-110">**file**</span></span>  | <span data-ttu-id="b5725-111">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-111">Optional attribute.</span></span><br><br><span data-ttu-id="b5725-112">사용자 지정 응용 프로그램 구성 설정이 포함 된 외부 파일의 상대 경로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="b5725-113">지정한 파일에 지정 된 설정의 같은 종류에는  **\<추가 >**,  **\<제거 >**, 및  **\<지우기 >** 요소와 해당 요소와 동일한 키/값 쌍이 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="b5725-114">지정 된 경로가 기본 구성 파일을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="b5725-115">이것은 이진 폴더는 Windows Forms 응용 프로그램에 대 한 (같은 */bin/debug*), 응용 프로그램 구성 파일의 위치에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="b5725-116">Web Forms 응용 프로그램에 대 한 응용 프로그램 루트에 상대적인 경로 여기서는 *web.config* 파일은 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="b5725-117">Note 지정된 된 파일을 찾을 수 없는 경우 런타임은 특성을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b5725-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b5725-118">Parent element</span></span>

|     | <span data-ttu-id="b5725-119">설명</span><span class="sxs-lookup"><span data-stu-id="b5725-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b5725-120">**\<구성 >** 요소</span><span class="sxs-lookup"><span data-stu-id="b5725-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="b5725-121">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b5725-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b5725-122">Child elements</span></span>

|     | <span data-ttu-id="b5725-123">설명</span><span class="sxs-lookup"><span data-stu-id="b5725-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b5725-124">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="b5725-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="b5725-125">사용자 지정 응용 프로그램 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="b5725-126">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="b5725-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="b5725-127">모든 이전에 정의 된 응용 프로그램 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="b5725-128">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="b5725-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="b5725-129">이전에 정의 된 응용 프로그램 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b5725-130">설명</span><span class="sxs-lookup"><span data-stu-id="b5725-130">Remarks</span></span>

<span data-ttu-id="b5725-131">**\<g s >** 데이터베이스 연결 문자열, 파일 경로, XML 웹 서비스 Url에 대 한 사용자 지정 구성 정보 등의 사용자 지정 응용 프로그램 구성 정보를 저장 하는 요소는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="b5725-132">에 지정 된 키/값 쌍의  **\<appSettings >** 요소가 사용 하 여 코드에 액세스 하는 <xref:System.Configuration.ConfigurationSettings> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="b5725-133">사용할 수는 **파일** 특성에  **\<g s >** 의 요소는 *Web.config* 및 응용 프로그램 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="b5725-134">추가 설정을 제공 하거나에 지정 된 설정을 재정의 하는 구성 파일을 지정 하는이 특성은  **\<g s >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="b5725-135">**파일** 특성은 사용자가 응용 프로그램 구성 파일에 지정 된 프로젝트 설정을 재정의 하려는 경우 처럼 소스 제어 팀 개발 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="b5725-136">지정 된 구성 파일의 **파일** 특성의 루트 노드에 있어야 합니다.  **\<g s >** 대신  **\<구성 >**.</span><span class="sxs-lookup"><span data-stu-id="b5725-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="b5725-137">예제</span><span class="sxs-lookup"><span data-stu-id="b5725-137">Example</span></span>

<span data-ttu-id="b5725-138">다음 예제에서는 사용자 지정 응용 프로그램 설정을 정의하는 외부 응용 프로그램 설정 파일(*custom.config*)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="b5725-139">다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 응용 프로그램 설정을 지정하는 응용 프로그램 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="b5725-140">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b5725-140">Configuration file</span></span>

<span data-ttu-id="b5725-141">이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b5725-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5725-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="b5725-142">See also</span></span>

[<span data-ttu-id="b5725-143">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b5725-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
