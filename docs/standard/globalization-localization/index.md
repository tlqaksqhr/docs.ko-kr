---
title: .NET 응용 프로그램 전역화 및 지역화
ms.date: 06/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- international applications [.NET]
- globalization [.NET], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f03935c1ee38cec4ee20c4306213be484933f0bb
ms.sourcegitcommit: 6c480773ae896f45af4671fb3e26611a50e4dd81
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2018
ms.locfileid: "35251001"
---
# <a name="globalizing-and-localizing-net-applications"></a><span data-ttu-id="58342-102">.NET 응용 프로그램 전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="58342-102">Globalizing and localizing .NET applications</span></span>
<span data-ttu-id="58342-103">하나 이상의 언어로 지역화할 수 있는 응용 프로그램을 포함하여 [지역화 대비 응용 프로그램](http://msdn.microsoft.com/goglobal/bb978433.aspx)의 개발에는 전역화, 지역화 가능성 검토 및 지역화의 세 가지 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58342-103">Developing a [world-ready application](http://msdn.microsoft.com/goglobal/bb978433.aspx), including an application that can be localized into one or more languages, involves three steps: globalization, localizability review, and localization.</span></span>  
  
 [<span data-ttu-id="58342-104">전역화</span><span class="sxs-lookup"><span data-stu-id="58342-104">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="58342-105">이 단계에는 문화적, 언어적으로 중립적이고 지역화된 사용자 인터페이스 및 모든 사용자의 지역 데이터를 지원하는 응용 프로그램을 디자인하고 코딩하는 데 과정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58342-105">This step involves designing and coding an application that is culture-neutral and language-neutral, and that supports localized user interfaces and regional data for all users.</span></span> <span data-ttu-id="58342-106">문화권별 가정을 기준으로 하지 않는 디자인 및 프로그래밍 결정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58342-106">It involves making design and programming decisions that are not based on culture-specific assumptions.</span></span> <span data-ttu-id="58342-107">전역화된 응용 프로그램은 지역화되지 않아도 하나 이상의 언어로 비교적 쉽게 지역화될 수 있도록 설계 및 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="58342-107">While a globalized application is not localized, it nevertheless is designed and written so that it can be subsequently localized into one or more languages with relative ease.</span></span>  
  
 [<span data-ttu-id="58342-108">지역화 가능성 검토</span><span class="sxs-lookup"><span data-stu-id="58342-108">Localizability review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="58342-109">이 단계에는 손쉽게 지역화할 수 있는지 확인하고 지역화하는 데 발생할 수 있는 장애물을 식별하도록 응용 프로그램의 코드 및 디자인을 검토하고 응용 프로그램의 실행 파일 코드를 리소스와 분리할 수 있는지를 확인하는 데 과정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58342-109">This step involves reviewing an application's code and design to ensure that it can be localized easily and to identify potential roadblocks for localization, and verifying that the application's executable code is separated from its resources.</span></span> <span data-ttu-id="58342-110">전역화 단계가 유효한 경우 지역화 검토는 전역화 중에 선택한 디자인과 코딩을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-110">If the globalization stage was effective, the localizability review will confirm the design and coding choices made during globalization.</span></span> <span data-ttu-id="58342-111">또한 지역화 가능성 단계에서 남아 있는 문제를 파악하여 지역화 단계에서 응용 프로그램의 소스 코드를 수정할 필요가 없도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58342-111">The localizability stage may also identify any remaining issues so that an application's source code doesn't have to be modified during the localization stage.</span></span>  
  
 [<span data-ttu-id="58342-112">지역화</span><span class="sxs-lookup"><span data-stu-id="58342-112">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="58342-113">이 단계에서는 특정 문화권 또는 지역에 대해 응용 프로그램을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-113">This step involves customizing an application for specific cultures or regions.</span></span> <span data-ttu-id="58342-114">전역화 및 지역화 가능성 확인 단계가 제대로 수행되었다면 지역화 작업은 주로 사용자 인터페이스의 번역으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="58342-114">If the globalization and localizability steps have been performed correctly, localization consists primarily of translating the user interface.</span></span>  
  
 <span data-ttu-id="58342-115">다음 세 단계에는 두 가지 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58342-115">Following these three steps provides two advantages:</span></span>  
  
-   <span data-ttu-id="58342-116">미국 영어와 같은 단일 문화권을 지원하도록 설계된 응용 프로그램을 추가 문화권을 지원하기 위해 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58342-116">It frees you from having to retrofit an application that is designed to support a single culture, such as U.S. English, to support additional cultures.</span></span>  
  
-   <span data-ttu-id="58342-117">그 결과, 보다 안정적이며 버그 발생이 적은 지역화된 응용 프로그램이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="58342-117">It results in localized applications that are more stable and have fewer bugs.</span></span>  
  
 <span data-ttu-id="58342-118">.NET에서는 전 세계를 대상으로 지역화되는 응용 프로그램 개발을 위해 광범위한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-118">.NET provides extensive support for the development of world-ready and localized applications.</span></span> <span data-ttu-id="58342-119">특히 .NET 클래스 라이브러리의 많은 형식 멤버는 현재 사용자의 문화권 또는 지정된 문화권의 규약을 반영하는 값을 반환함으로써 전역화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-119">In particular, many type members in the .NET class library aid globalization by returning values that reflect the conventions of either the current user's culture or a specified culture.</span></span> <span data-ttu-id="58342-120">또한 .NET은 응용 프로그램 지역화 프로세스를 용이하게 하는 위성 어셈블리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-120">Also, .NET supports satellite assemblies, which facilitate the process of localizing an application.</span></span>  
  
 <span data-ttu-id="58342-121">자세한 내용은 [세계화 설명서](/globalization/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58342-121">For additional information, see the [Globalization documentation](/globalization/).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58342-122">단원 내용</span><span class="sxs-lookup"><span data-stu-id="58342-122">In this section</span></span>  
 [<span data-ttu-id="58342-123">전역화</span><span class="sxs-lookup"><span data-stu-id="58342-123">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 <span data-ttu-id="58342-124">문화권과 언어에 중립적인 응용 프로그램을 디자인하고 코딩하는 것을 포함하여 지역화 대비 응용 프로그램을 만드는 첫 번째 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-124">Discusses the first stage of creating a world-ready application, which involves designing and coding an application that is culture-neutral and language-neutral.</span></span>  
  
 [<span data-ttu-id="58342-125">지역화 가능성 검토</span><span class="sxs-lookup"><span data-stu-id="58342-125">Localizability review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 <span data-ttu-id="58342-126">지역화하는 데 발생할 수 있는 장애물을 식별하는 것을 포함하여 지역화된 응용 프로그램을 만드는 두 번째 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-126">Discusses the second stage of creating a localized application, which involves identifying potential roadblocks to localization.</span></span>  
  
 [<span data-ttu-id="58342-127">지역화</span><span class="sxs-lookup"><span data-stu-id="58342-127">Localization</span></span>](../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="58342-128">특정 지역 또는 문화권에 대한 응용 프로그램 사용자 인터페이스 사용자 지정을 포함하는 지역화된 응용 프로그램을 만드는 최종 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-128">Discusses the final stage of creating a localized application, which involves customizing an application's user interface for specific regions or cultures.</span></span>  
  
 [<span data-ttu-id="58342-129">문화권을 구분하지 않는 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="58342-129">Culture-insensitive string operations</span></span>](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 <span data-ttu-id="58342-130">기본적으로 문화권에 따라 다른 .NET 메서드 및 클래스를 사용하여 문화권을 구분하지 않는 결과를 얻는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-130">Describes how to use .NET methods and classes that are culture-sensitive by default to obtain culture-insensitive results.</span></span>  
  
 [<span data-ttu-id="58342-131">지역화 대비 응용 프로그램 개발을 위한 최선의 구현 방법</span><span class="sxs-lookup"><span data-stu-id="58342-131">Best practices for developing world-ready applications</span></span>](../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md)  
 <span data-ttu-id="58342-132">전역화 및 지역화 구현과 world-ready ASP.NET 응용 프로그램 개발을 위한 최선의 구현 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-132">Describes the best practices to follow for globalization, localization, and developing world-ready ASP.NET applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="58342-133">참조</span><span class="sxs-lookup"><span data-stu-id="58342-133">Reference</span></span>  
 <span data-ttu-id="58342-134"><xref:System.Globalization?displayProperty=nameWithType> 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="58342-134"><xref:System.Globalization?displayProperty=nameWithType> namespace</span></span>  
 <span data-ttu-id="58342-135">언어, 국가/지역, 사용하는 달력, 날짜, 통화 및 숫자 형식 패턴, 문자열 정렬 순서 등의 문화권 관련 정보를 정의하는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-135">Contains classes that define culture-related information, including the language, the country/region, the calendars in use, the format patterns for dates, currency, and numbers, and the sort order for strings.</span></span>  
  
 <span data-ttu-id="58342-136"><xref:System.Resources> 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="58342-136"><xref:System.Resources> namespace</span></span>  
 <span data-ttu-id="58342-137">리소스를 만들고 조작하고 사용하기 위한 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-137">Provides classes for creating, manipulating, and using resources.</span></span>  
  
 <span data-ttu-id="58342-138"><xref:System.Text> 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="58342-138"><xref:System.Text> namespace</span></span>  
 <span data-ttu-id="58342-139">ASCII, ANSI, 유니코드 및 기타 문자 인코딩을 나타내는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-139">Contains classes representing ASCII, ANSI, Unicode, and other character encodings.</span></span>  
  
 [<span data-ttu-id="58342-140">Resgen.exe(리소스 파일 생성기)</span><span class="sxs-lookup"><span data-stu-id="58342-140">Resgen.exe (Resource File Generator)</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 <span data-ttu-id="58342-141">Resgen.exe를 사용하여 .txt 파일 및 .resx(XML 기반 리소스 형식) 파일을 공용 언어 런타임 바이너리 .resources 파일로 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-141">Describes how to use Resgen.exe to convert .txt files and XML-based resource format (.resx) files to common language runtime binary .resources files.</span></span>  
  
 [<span data-ttu-id="58342-142">Winres.exe(Windows Forms 리소스 편집기)</span><span class="sxs-lookup"><span data-stu-id="58342-142">Winres.exe (Windows Forms Resource Editor)</span></span>](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 <span data-ttu-id="58342-143">Winres.exe를 사용하여 Windows Forms 폼을 지역화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58342-143">Describes how to use Winres.exe to localize Windows Forms forms.</span></span>
