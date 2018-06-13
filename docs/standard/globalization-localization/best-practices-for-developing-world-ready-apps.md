---
title: 지역화 대비 응용 프로그램 개발을 위한 최선의 구현 방법
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- global applications, best practices
- world-ready applications, best practices
- globalization [.NET Framework], best practices
- international applications [.NET Framework], best practices
ms.assetid: f08169c7-aad8-4ec3-9a21-9ebd3b89986c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 804f92ddd564f057157598c3cf62106d1a7d5318
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578205"
---
# <a name="best-practices-for-developing-world-ready-applications"></a><span data-ttu-id="bdb87-102">지역화 대비 응용 프로그램 개발을 위한 최선의 구현 방법</span><span class="sxs-lookup"><span data-stu-id="bdb87-102">Best Practices for Developing World-Ready Applications</span></span>
<span data-ttu-id="bdb87-103">이 단원에서는 지역화 대비 응용 프로그램을 개발할 때 따라야 할 최선의 구현 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-103">This section describes the best practices to follow when developing world-ready applications.</span></span>  
  
## <a name="globalization-best-practices"></a><span data-ttu-id="bdb87-104">최상의 전역화 방법</span><span class="sxs-lookup"><span data-stu-id="bdb87-104">Globalization Best Practices</span></span>  
  
1.  <span data-ttu-id="bdb87-105">응용 프로그램에서 내부적으로 유니코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-105">Make your application Unicode internally.</span></span>  
  
2.  <span data-ttu-id="bdb87-106"><xref:System.Globalization> 네임스페이스에서 제공하는 문화권 인식 클래스를 사용하여 데이터를 조작하고 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-106">Use the culture-aware classes provided by the <xref:System.Globalization> namespace to manipulate and format data.</span></span>  
  
    -   <span data-ttu-id="bdb87-107">정렬할 때는 <xref:System.Globalization.SortKey> 클래스 및 <xref:System.Globalization.CompareInfo> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-107">For sorting, use the <xref:System.Globalization.SortKey> class and the <xref:System.Globalization.CompareInfo> class.</span></span>  
  
    -   <span data-ttu-id="bdb87-108">문자열을 비교할 때는 <xref:System.Globalization.CompareInfo> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-108">For string comparisons, use the <xref:System.Globalization.CompareInfo> class.</span></span>  
  
    -   <span data-ttu-id="bdb87-109">날짜 및 시간 형식을 지정할 때는 <xref:System.Globalization.DateTimeFormatInfo> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-109">For date and time formatting, use the <xref:System.Globalization.DateTimeFormatInfo> class.</span></span>  
  
    -   <span data-ttu-id="bdb87-110">숫자 형식을 지정할 때는 <xref:System.Globalization.NumberFormatInfo> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-110">For numeric formatting, use the <xref:System.Globalization.NumberFormatInfo> class.</span></span>  
  
    -   <span data-ttu-id="bdb87-111">그레고리오력 및 그레고리오력이 아닌 달력을 사용하려면 <xref:System.Globalization.Calendar> 클래스 또는 특정 달력 구현 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-111">For Gregorian and non-Gregorian calendars, use the <xref:System.Globalization.Calendar> class or one of the specific calendar implementations.</span></span>  
  
3.  <span data-ttu-id="bdb87-112"><xref:System.Globalization.CultureInfo?displayProperty=nameWithType> 클래스에서 제공하는 문화권 속성 설정을 적절한 상황에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-112">Use the culture property settings provided by the <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> class in the appropriate situations.</span></span> <span data-ttu-id="bdb87-113">날짜 및 시간 또는 숫자 형식 지정과 같은 형식 지정 작업에는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-113">Use the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> property for formatting tasks, such as date and time or numeric formatting.</span></span> <span data-ttu-id="bdb87-114">리소스를 검색하려면 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-114">Use the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property to retrieve resources.</span></span> <span data-ttu-id="bdb87-115">`CurrentCulture` 및 `CurrentUICulture` 속성을 스레드별로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-115">Note that the `CurrentCulture` and `CurrentUICulture` properties can be set per thread.</span></span>  
  
4.  <span data-ttu-id="bdb87-116">응용 프로그램에서 <xref:System.Text> 네임스페이스의 인코딩 클래스를 사용하여 다양한 인코딩 간에 데이터를 읽고 쓸 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-116">Enable your application to read and write data to and from a variety of encodings by using the encoding classes in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="bdb87-117">ASCII 데이터가 입력될 것으로 예상하지 말고,</span><span class="sxs-lookup"><span data-stu-id="bdb87-117">Do not assume ASCII data.</span></span> <span data-ttu-id="bdb87-118">사용자가 텍스트를 입력할 수 있는 모든 위치에 국제 문자가 제공될 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-118">Assume that international characters will be supplied anywhere a user can enter text.</span></span> <span data-ttu-id="bdb87-119">예를 들어, 응용 프로그램에서는 서버 이름, 디렉터리, 파일 이름, 사용자 이름 및 URL에서 국제 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-119">For example, the application should accept international characters in server names, directories, file names, user names, and URLs.</span></span>  
  
5.  <span data-ttu-id="bdb87-120"><xref:System.Text.UTF8Encoding> 클래스를 사용할 때는 보안상의 이유로 이 클래스가 제공하는 오류 검색 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-120">When using the <xref:System.Text.UTF8Encoding> class, for security reasons, use the error detection feature offered by this class.</span></span> <span data-ttu-id="bdb87-121">오류 검색 기능을 설정하기 위해 응용 프로그램에서는 `throwOnInvalidBytes` 매개 변수를 사용하는 생성자를 사용하여 클래스의 인스턴스를 만든 다음 이 매개 변수의 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-121">To turn on the error detection feature, the application creates an instance of the class using the constructor that takes a `throwOnInvalidBytes` parameter and sets the value of this parameter to `true`.</span></span>  
  
6.  <span data-ttu-id="bdb87-122">가능하면 문자열을 일련의 개별 문자가 아니라 전체 문자열로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-122">Whenever possible, handle strings as entire strings instead of as a series of individual characters.</span></span> <span data-ttu-id="bdb87-123">이것은 하위 문자열을 검색하거나 정렬할 때 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-123">This is especially important when sorting or searching for substrings.</span></span> <span data-ttu-id="bdb87-124">이를 통해 조합된 문자의 구문을 분석할 때 발생하는 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-124">This will prevent problems associated with parsing combined characters.</span></span>  
  
7.  <span data-ttu-id="bdb87-125"><xref:System.Drawing> 네임스페이스에서 제공하는 클래스를 사용하여 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-125">Display text using the classes provided by the <xref:System.Drawing> namespace.</span></span>  
  
8.  <span data-ttu-id="bdb87-126">운영 체제 간에 일관성을 유지하려면 사용자 설정에 따라 <xref:System.Globalization.CultureInfo>가 재정의되지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-126">For consistency across operating systems, do not allow user settings to override <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="bdb87-127">`CultureInfo` 매개 변수를 사용하는 `useUserOverride` 생성자를 사용하여 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-127">Use the `CultureInfo` constructor that accepts a `useUserOverride` parameter and set it to `false`.</span></span>  
  
9. <span data-ttu-id="bdb87-128">국제 데이터를 사용하여 국제 운영 체제 버전에서 응용 프로그램의 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-128">Test your application functionality on international operating system versions, using international data.</span></span>  
  
10. <span data-ttu-id="bdb87-129">문자열 비교 또는 대/소문자 변경 작업의 결과에 따라 보안을 결정하는 경우 응용 프로그램에서 문화권을 구분하지 않는 작업을 수행하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-129">If a security decision is based on the result of a string comparison or case change operation, have the application perform a culture-insensitive operation.</span></span> <span data-ttu-id="bdb87-130">이러한 구현 방법을 사용하면 결과가 `CultureInfo.CurrentCulture` 값의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-130">This practice ensures that the result is not affected by the value of `CultureInfo.CurrentCulture`.</span></span> <span data-ttu-id="bdb87-131">문화권 구분 문자열 비교로 인해 어떻게 일관되지 않은 결과가 나타날 수 있는지에 대한 예제를 보려면 [문자열 사용에 대한 모범 사례](../../../docs/standard/base-types/best-practices-strings.md)의 “현재 문화권을 사용하는 문자열 비교” 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdb87-131">See the "String Comparisons that Use the Current Culture" section of [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) for an example that demonstrates how culture-sensitive string comparisons can produce inconsistent results.</span></span>  
  
## <a name="localization-best-practices"></a><span data-ttu-id="bdb87-132">최상의 지역화 방법</span><span class="sxs-lookup"><span data-stu-id="bdb87-132">Localization Best Practices</span></span>  
  
1.  <span data-ttu-id="bdb87-133">지역화할 수 있는 모든 리소스를 별도의 리소스 전용 DLL로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-133">Move all localizable resources to separate resource-only DLLs.</span></span> <span data-ttu-id="bdb87-134">지역화 가능한 리소스에는 문자열, 오류 메시지, 대화 상자, 메뉴 및 포함된 개체 리소스 등과 같은 사용자 인터페이스 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-134">Localizable resources include user interface elements, such as strings, error messages, dialog boxes, menus, and embedded object resources.</span></span>  
  
2.  <span data-ttu-id="bdb87-135">문자열이나 사용자 인터페이스 리소스를 하드 코드하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bdb87-135">Do not hardcode strings or user interface resources.</span></span>  
  
3.  <span data-ttu-id="bdb87-136">지역화할 수 없는 리소스를 리소스 전용 DLL에 두지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bdb87-136">Do not put nonlocalizable resources into the resource-only DLLs.</span></span> <span data-ttu-id="bdb87-137">변환기에 혼동을 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-137">This causes confusion for translators.</span></span>  
  
4.  <span data-ttu-id="bdb87-138">연결된 구에서 런타임에 작성된 복합 문자열을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bdb87-138">Do not use composite strings that are built at run time from concatenated phrases.</span></span> <span data-ttu-id="bdb87-139">복합 문자열은 일부 언어에만 적용되는 영문법 순서를 가정하는 경우가 많으므로 지역화하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-139">Composite strings are difficult to localize because they often assume an English grammatical order that does not apply to all languages.</span></span>  
  
5.  <span data-ttu-id="bdb87-140">"Empty Folder"와 같이 문자열이 문자열 구성 요소의 문법적 역할에 따라 다르게 변환될 수 있는 애매한 구문은 피합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-140">Avoid ambiguous constructs such as "Empty Folder" where the strings can be translated differently depending on the grammatical roles of the string components.</span></span> <span data-ttu-id="bdb87-141">예를 들어, "empty"는 동사나 형용사로 사용할 수 있으므로 이탈리아어나 프랑스어와 같은 언어에서는 다르게 번역될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-141">For example, "empty" can be either a verb or an adjective, which can lead to different translations in languages such as Italian or French.</span></span>  
  
6.  <span data-ttu-id="bdb87-142">응용 프로그램에서 텍스트가 들어 있는 이미지나 아이콘은 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-142">Avoid using images and icons that contain text in your application.</span></span> <span data-ttu-id="bdb87-143">이러한 경우에는 지역화 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-143">They are expensive to localize.</span></span>  
  
7.  <span data-ttu-id="bdb87-144">사용자 인터페이스에서 문자열 길이를 확장할 수 있도록 충분한 공간을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-144">Allow plenty of room for the length of strings to expand in the user interface.</span></span> <span data-ttu-id="bdb87-145">일부 언어에서는 다른 언어와 비교하여 구에 50-75%의 공간이 더 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-145">In some languages, phrases can require 50-75 percent more space than they need in other languages.</span></span>  
  
8.  <span data-ttu-id="bdb87-146"><xref:System.Resources.ResourceManager?displayProperty=nameWithType> 클래스를 사용하여 문화권에 따라 리소스를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-146">Use the <xref:System.Resources.ResourceManager?displayProperty=nameWithType> class to retrieve resources based on culture.</span></span>  
  
9. <span data-ttu-id="bdb87-147">[Windows Forms 리소스 편집기(Winres.exe)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)를 사용하여 지역화할 수 있도록 Visual Studio를 사용하여 Windows Forms 대화 상자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-147">Use Visual Studio to create Windows Forms dialog boxes, so that they can be localized using the [Windows Forms Resource Editor (Winres.exe)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span> <span data-ttu-id="bdb87-148">Windows Forms 대화 상자는 직접 코딩하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bdb87-148">Do not code Windows Forms dialog boxes by hand.</span></span>  
  
10. <span data-ttu-id="bdb87-149">전문적인 지역화(번역) 작업을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-149">Arrange for professional localization (translation).</span></span>  
  
11. <span data-ttu-id="bdb87-150">리소스 만들기 및 지역화에 대한 자세한 설명을 보려면 [응용 프로그램의 리소스](../../../docs/framework/resources/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdb87-150">For a complete description of creating and localizing resources, see [Resources in Applications](../../../docs/framework/resources/index.md).</span></span>  
  
## <a name="globalization-best-practices-for-aspnet-applications"></a><span data-ttu-id="bdb87-151">ASP.NET 응용 프로그램을 위한 최상의 전역화 방법</span><span class="sxs-lookup"><span data-stu-id="bdb87-151">Globalization Best Practices for ASP.NET Applications</span></span>  
  
1.  <span data-ttu-id="bdb87-152">응용 프로그램에서 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> 및 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> 속성을 명시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-152">Explicitly set the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> and <xref:System.Globalization.CultureInfo.CurrentCulture%2A> properties in your application.</span></span> <span data-ttu-id="bdb87-153">기본값을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bdb87-153">Do not rely on defaults.</span></span>  
  
2.  <span data-ttu-id="bdb87-154">ASP.NET 응용 프로그램은 관리되는 응용 프로그램이므로 다른 응용 프로그램의 경우와 같은 클래스를 사용하여 문화권 관련 정보를 검색, 표시 및 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-154">Note that ASP.NET applications are managed applications and therefore can use the same classes as other managed applications for retrieving, displaying, and manipulating information based on culture.</span></span>  
  
3.  <span data-ttu-id="bdb87-155">ASP.NET에 다음 세 가지 인코딩을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-155">Be aware that you can specify the following three types of encodings in ASP.NET:</span></span>  
  
    -   <span data-ttu-id="bdb87-156">requestEncoding은 클라이언트 브라우저에서 받은 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-156">requestEncoding specifies the encoding received from the client's browser.</span></span>  
  
    -   <span data-ttu-id="bdb87-157">responseEncoding은 클라이언트 브라우저로 보낼 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-157">responseEncoding specifies the encoding to send to the client browser.</span></span> <span data-ttu-id="bdb87-158">대부분의 경우 이 인코딩은 requestEncoding에 지정된 것과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-158">In most situations, this encoding should be the same as that specified for requestEncoding.</span></span>  
  
    -   <span data-ttu-id="bdb87-159">fileEncoding은 aspx, .asmx 및 .asax 파일 구문 분석의 기본 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-159">fileEncoding specifies the default encoding for .aspx, .asmx, and .asax file parsing.</span></span>  
  
4.  <span data-ttu-id="bdb87-160">ASP.NET 응용 프로그램의 다음 세 위치에서 requestEncoding, responseEncoding, fileEncoding, culture 및 uiCulture 특성의 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-160">Specify the values for the requestEncoding, responseEncoding, fileEncoding, culture, and uiCulture attributes in the following three places in an ASP.NET application:</span></span>  
  
    -   <span data-ttu-id="bdb87-161">Web.config 파일의 전역화 섹션에서.</span><span class="sxs-lookup"><span data-stu-id="bdb87-161">In the globalization section of a Web.config file.</span></span> <span data-ttu-id="bdb87-162">이 파일은 ASP.NET 응용 프로그램에 대해 외부 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-162">This file is external to the ASP.NET application.</span></span> <span data-ttu-id="bdb87-163">자세한 내용은 [\<globalization> 요소](https://msdn.microsoft.com/library/e2dffc8e-ebd2-439b-a2fd-e3ac5e620da7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdb87-163">For more information, see [\<globalization> Element](https://msdn.microsoft.com/library/e2dffc8e-ebd2-439b-a2fd-e3ac5e620da7).</span></span>  
  
    -   <span data-ttu-id="bdb87-164">페이지 지시문에서.</span><span class="sxs-lookup"><span data-stu-id="bdb87-164">In a page directive.</span></span> <span data-ttu-id="bdb87-165">응용 프로그램이 페이지에 있는 경우 파일이 이미 읽혀진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-165">Note that, when an application is in a page, the file has already been read.</span></span> <span data-ttu-id="bdb87-166">따라서 너무 늦었으므로 fileEncoding 및 requestEncoding을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-166">Therefore, it is too late to specify fileEncoding and requestEncoding.</span></span> <span data-ttu-id="bdb87-167">uiCulture, Culture 및 responseEncoding만 페이지 지시문에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-167">Only uiCulture, Culture, and responseEncoding can be specified in a page directive.</span></span>  
  
    -   <span data-ttu-id="bdb87-168">프로그램 방식으로 응용 프로그램 코드에서.</span><span class="sxs-lookup"><span data-stu-id="bdb87-168">Programmatically in application code.</span></span> <span data-ttu-id="bdb87-169">이 설정은 요청마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-169">This setting can vary per request.</span></span> <span data-ttu-id="bdb87-170">페이지 지시문의 경우와 마찬가지로 해당 응용 프로그램 코드에 도달되면 이미 너무 늦었으므로 fileEncoding 및 requestEncoding을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-170">As with a page directive, by the time the application's code is reached it is too late to specify fileEncoding and requestEncoding.</span></span> <span data-ttu-id="bdb87-171">uiCulture, Culture 및 responseEncoding만 응용 프로그램 코드에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-171">Only uiCulture, Culture, and responseEncoding can be specified in application code.</span></span>  
  
5.  <span data-ttu-id="bdb87-172">uiCulture 값은 브라우저 허용 언어로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb87-172">Note that the uiCulture value can be set to the browser accept language.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb87-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdb87-173">See Also</span></span>  
 [<span data-ttu-id="bdb87-174">전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="bdb87-174">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="bdb87-175">데스크톱 앱의 리소스</span><span class="sxs-lookup"><span data-stu-id="bdb87-175">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
