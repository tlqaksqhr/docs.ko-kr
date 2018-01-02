---
title: "응용 프로그램 설정 스키마"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
caps.latest.revision: "3"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 3581c8079132de5f1faad4a01e6b43c8e4833316
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="application-settings-schema"></a><span data-ttu-id="5293a-102">응용 프로그램 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="5293a-102">Application Settings schema</span></span>

<span data-ttu-id="5293a-103">응용 프로그램 설정을 저장 하 고 응용 프로그램 범위 및 사용자 범위 설정을 검색 하는 Windows Forms 또는 ASP.NET 응용 프로그램을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="5293a-104">이 컨텍스트에서 *설정* 는 응용 프로그램 관련 또는 현재 사용자에 게 특정 수 있는 정보의 일부-사용자에 게 데이터베이스 연결 문자열에서 모든 항목의 기본 창 크기 기본 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="5293a-105">Windows Forms 응용 프로그램에서 응용 프로그램 설정을 사용 하 여 기본적으로는 <xref:System.Configuration.LocalFileSettingsProvider> 클래스를 사용 하 여.NET 구성 시스템이 설정을 XML 구성 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="5293a-106">응용 프로그램 설정에서 사용 하는 파일에 대 한 자세한 내용은 참조 [응용 프로그램 설정 아키텍처](~/docs/framework/winforms/advanced/application-settings-architecture.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-106">For more information about the files used by application settings, see [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="5293a-107">응용 프로그램 설정을 사용 하 여 구성 파일의 일부로 다음과 같은 요소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="5293a-108">요소</span><span class="sxs-lookup"><span data-stu-id="5293a-108">Element</span></span>                    | <span data-ttu-id="5293a-109">설명</span><span class="sxs-lookup"><span data-stu-id="5293a-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="5293a-110">**\<applicationSettings >**</span><span class="sxs-lookup"><span data-stu-id="5293a-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="5293a-111">모든 포함  **\<설정 >** 태그 응용 프로그램에 특정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="5293a-112">**\<g s >**</span><span class="sxs-lookup"><span data-stu-id="5293a-112">**\<userSettings>**</span></span>        | <span data-ttu-id="5293a-113">모든 포함  **\<설정 >** 현재 사용자에 게 특정 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="5293a-114">**\<설정 >**</span><span class="sxs-lookup"><span data-stu-id="5293a-114">**\<setting>**</span></span>             | <span data-ttu-id="5293a-115">설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-115">Defines a setting.</span></span> <span data-ttu-id="5293a-116">자식 요소  **\<applicationSettings >** 또는  **\<g s >**합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="5293a-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="5293a-117">**\<value>**</span></span>               | <span data-ttu-id="5293a-118">설정 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-118">Defines a setting's value.</span></span> <span data-ttu-id="5293a-119">자식  **\<설정 >**합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="5293a-120">\<applicationSettings > 요소</span><span class="sxs-lookup"><span data-stu-id="5293a-120">\<applicationSettings> element</span></span>

<span data-ttu-id="5293a-121">이 요소는 모든 포함  **\<설정 >** 클라이언트 컴퓨터에서 응용 프로그램의 인스턴스에 관련 된 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="5293a-122">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="5293a-123">\<g s > 요소</span><span class="sxs-lookup"><span data-stu-id="5293a-123">\<userSettings> element</span></span>

<span data-ttu-id="5293a-124">이 요소는 모든 포함  **\<설정 >** 응용 프로그램 현재 사용 하는 사용자에만 적용 되는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="5293a-125">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="5293a-126">\<설정 > 요소</span><span class="sxs-lookup"><span data-stu-id="5293a-126">\<setting> element</span></span>

<span data-ttu-id="5293a-127">이 요소는 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-127">This element defines a setting.</span></span> <span data-ttu-id="5293a-128">다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-128">It has the following attributes.</span></span>

| <span data-ttu-id="5293a-129">특성</span><span class="sxs-lookup"><span data-stu-id="5293a-129">Attribute</span></span>        | <span data-ttu-id="5293a-130">설명</span><span class="sxs-lookup"><span data-stu-id="5293a-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="5293a-131">**name**</span><span class="sxs-lookup"><span data-stu-id="5293a-131">**name**</span></span>         | <span data-ttu-id="5293a-132">필수.</span><span class="sxs-lookup"><span data-stu-id="5293a-132">Required.</span></span> <span data-ttu-id="5293a-133">설정의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-133">The unique ID of the setting.</span></span> <span data-ttu-id="5293a-134">Visual Studio를 통해 만든 설정은 이름으로 저장 됩니다 `ProjectName.Properties.Settings`합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="5293a-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="5293a-135">**serializedAs**</span></span> | <span data-ttu-id="5293a-136">필수.</span><span class="sxs-lookup"><span data-stu-id="5293a-136">Required.</span></span> <span data-ttu-id="5293a-137">값을 텍스트로 직렬화 하는 작업에 사용할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="5293a-138">올바른 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-138">Valid values are:</span></span><br><br><span data-ttu-id="5293a-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="5293a-139">- `string`.</span></span> <span data-ttu-id="5293a-140">값을 사용 하 여 문자열 직렬화는 <xref:System.ComponentModel.TypeConverter>합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="5293a-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="5293a-141">- `xml`.</span></span> <span data-ttu-id="5293a-142">값은 XML serialization을 사용 하 여 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="5293a-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="5293a-143">- `binary`.</span></span> <span data-ttu-id="5293a-144">값은 이진 serialization을 사용 하 여 텍스트로 인코딩된 이진 형식으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="5293a-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="5293a-145">- `custom`.</span></span> <span data-ttu-id="5293a-146">설정 공급자가이 설정의 내재 된 지식이 직렬화 및 역직렬화 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="5293a-147">\<값 > 요소</span><span class="sxs-lookup"><span data-stu-id="5293a-147">\<value> element</span></span>

<span data-ttu-id="5293a-148">이 요소는 설정의 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="5293a-149">예</span><span class="sxs-lookup"><span data-stu-id="5293a-149">Example</span></span>

<span data-ttu-id="5293a-150">다음 예제에서는 두 개의 응용 프로그램 범위 설정 및 두 개의 사용자 범위 설정을 정의 하는 응용 프로그램 설정 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5293a-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5293a-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5293a-151">See also</span></span>

<span data-ttu-id="5293a-152">[응용 프로그램 설정 개요](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="5293a-152">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="5293a-153">응용 프로그램 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="5293a-153">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
