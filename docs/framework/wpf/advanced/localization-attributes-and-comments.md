---
title: 지역화 특성 및 주석
ms.date: 03/30/2017
helpviewer_keywords:
- localization [WPF], attributes
- localization [WPF], comments
ms.assetid: ead2d9ac-b709-4ec1-a924-39927a29d02f
ms.openlocfilehash: 7cfcc9fa4dc3bc1450febb39500b7d96f92beac6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547269"
---
# <a name="localization-attributes-and-comments"></a><span data-ttu-id="873ec-102">지역화 특성 및 주석</span><span class="sxs-lookup"><span data-stu-id="873ec-102">Localization Attributes and Comments</span></span>
[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]<span data-ttu-id="873ec-103"> 소스 코드 내의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 지역화 주석은 속성이며 개발자에 의해 제공되어 지역화에 대한 규칙과 힌트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-103"> localization comments are properties, inside [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] source code, supplied by developers to provide rules and hints for localization.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="873ec-104"> 지역화 주석에는 두 가지 정보 집합(지역화 가능성 특성 및 자유 형식 지역화 주석)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-104"> localization comments contain two sets of information: localizability attributes and free-form localization comments.</span></span> <span data-ttu-id="873ec-105">지역화 가능성 특성은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지역화 API가 사용하여 지역화할 리소스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-105">Localizability attributes are used by the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Localization API to indicate which resources are to be localized.</span></span> <span data-ttu-id="873ec-106">자유 형식 주석은 응용 프로그램 작성자가 포함하려고 하는 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-106">Free-form comments are any information that the application author wants to include.</span></span>  
  

  
<a name="Localizer_Comments_"></a>   
## <a name="localization-comments"></a><span data-ttu-id="873ec-107">지역화 주석</span><span class="sxs-lookup"><span data-stu-id="873ec-107">Localization Comments</span></span>  
 <span data-ttu-id="873ec-108">태그 응용 프로그램 작성자에게 텍스트 길이, 글꼴 패밀리 또는 글꼴 크기에 대한 제약 조건과 같은 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]의 특정 요소에 대한 요구 사항이 있는 경우 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 코드에 주석을 사용하여 이 정보를 지역화 담당자에게 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-108">If markup application authors have requirements for specific elements in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], such as constraints on text length, font family, or font size, they can convey this information to localizers with comments in the [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] code.</span></span> <span data-ttu-id="873ec-109">주석을 소스 코드에 추가하는 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-109">The process for adding comments to source code is as follows:</span></span>  
  
1.  <span data-ttu-id="873ec-110">응용 프로그램 개발자는 지역화 주석을 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 소스 코드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-110">Application developer adds localization comments to [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] source code.</span></span>  
  
2.  <span data-ttu-id="873ec-111">빌드 프로세스 중에 자유 형식 지역화 주석을 어셈블리에 남길지, 주석의 일부를 제거할지, 모든 주석을 제거할지 여부를 .proj 파일에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-111">During the build process, you can specify in the .proj file whether to leave the free-form localization comments in the assembly, strip out part of the comments, or strip out all the comments.</span></span> <span data-ttu-id="873ec-112">제거된 주석은 별도의 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-112">The stripped-out comments are placed in a separate file.</span></span> <span data-ttu-id="873ec-113">`LocalizationDirectivesToLocFile` 태그를 사용하여 옵션을 지정합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-113">You specify your option using a `LocalizationDirectivesToLocFile` tag, eg:</span></span>  
  
     <span data-ttu-id="873ec-114">`<LocalizationDirectivesToLocFile>` *값* `</LocalizationDirectivesToLocFile>`</span><span class="sxs-lookup"><span data-stu-id="873ec-114">`<LocalizationDirectivesToLocFile>` *value* `</LocalizationDirectivesToLocFile>`</span></span>  
  
3.  <span data-ttu-id="873ec-115">할당할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-115">The values that can be assigned are:</span></span>  
  
    -   <span data-ttu-id="873ec-116">**None** - 주석과 특성이 모두 어셈블리 안에 유지되고 별도의 파일이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-116">**None** - Both comments and attributes stay inside the assembly and no separate file is generated.</span></span>  
  
    -   <span data-ttu-id="873ec-117">**CommentsOnly** - 어셈블리에서 주석만 제거하고 별도의 LocFile 파일에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-117">**CommentsOnly** - Strips only the comments from the assembly and places them in the separate LocFile.</span></span>  
  
    -   <span data-ttu-id="873ec-118">**All** - 주석과 특성을 어셈블리에서 모두 제거하고 둘 다 별도의 LocFile에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-118">**All** - Strips both the comments and the attributes from the assembly and places them both in a separate LocFile.</span></span>  
  
4.  <span data-ttu-id="873ec-119">지역화 가능한 리소스가 [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)]에서 추출된 경우 지역화 가능성 특성을 [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)] 지역화 API에서 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-119">When localizable resources are extracted from [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)], the localizability attributes are respected by the [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)] Localization API.</span></span>  
  
5.  <span data-ttu-id="873ec-120">자유 형식 주석만 포함하는 지역화 주석 파일은 나중에 지역화 프로세스에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-120">Localization comment files, containing only free-form comments, are incorporated into the localization process at a later time.</span></span>  
  
 <span data-ttu-id="873ec-121">다음 예제에서는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 파일에 지역화 주석을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-121">The following example shows how to add localization comments to a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file.</span></span>  
  
 `<TextBlock x:Id = "text01"`  
  
 `FontFamily = "Microsoft Sans Serif"`  
  
 `FontSize = "12"`  
  
 `Localization.Attributes = "$Content (Unmodifiable Readable Text)`  
  
 `FontFamily (Unmodifiable Readable)"`  
  
 `Localization.Comments = "$Content (Trademark)`  
  
 `FontSize (Trademark font size)" >`  
  
 `Microsoft`  
  
 `</TextBlock>`  
  
 <span data-ttu-id="873ec-122">위 샘플에서 Localization.Attributes 섹션에는 지역화 특성이 포함되어 있고 Localization.Comments 섹션에는 자유 형식 주석이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-122">In the previous sample the Localization.Attributes section contains the localization attributes and the Localization.Comments section the free-form comments.</span></span> <span data-ttu-id="873ec-123">다음 표에서는 특성 및 주석과 함께 지역화 담당자에게 어떤 의미가 있는지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-123">The following tables show the attributes and comments and their meaning to the localizer.</span></span>  
  
|<span data-ttu-id="873ec-124">지역화 특성</span><span class="sxs-lookup"><span data-stu-id="873ec-124">Localization attributes</span></span>|<span data-ttu-id="873ec-125">의미</span><span class="sxs-lookup"><span data-stu-id="873ec-125">Meaning</span></span>|  
|-----------------------------|-------------|  
|<span data-ttu-id="873ec-126">$Content (Unmodifiable Readable Text)</span><span class="sxs-lookup"><span data-stu-id="873ec-126">$Content (Unmodifiable Readable Text)</span></span>|<span data-ttu-id="873ec-127">TextBlock 요소의 콘텐츠를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-127">Contents of the TextBlock element cannot be modified.</span></span> <span data-ttu-id="873ec-128">지역화 담당자는 “Microsoft” 단어를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-128">Localizers cannot change the word "Microsoft".</span></span> <span data-ttu-id="873ec-129">콘텐츠는 지역화 담당자가 볼 수 있습니다(읽기 가능).</span><span class="sxs-lookup"><span data-stu-id="873ec-129">The content is visible (Readable) to the localizer.</span></span> <span data-ttu-id="873ec-130">콘텐츠의 범주는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-130">The category of the content is text.</span></span>|  
|<span data-ttu-id="873ec-131">FontFamily (Unmodifiable Readable)</span><span class="sxs-lookup"><span data-stu-id="873ec-131">FontFamily (Unmodifiable Readable)</span></span>|<span data-ttu-id="873ec-132">TextBlock 요소의 글꼴 패밀리 속성은 변경할 수 없지만 지역화 담당자가 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-132">The font family property of the TextBlock element cannot be changed but it is visible to the localizer.</span></span>|  
  
|<span data-ttu-id="873ec-133">지역화 자유 형식 주석</span><span class="sxs-lookup"><span data-stu-id="873ec-133">Localization free-form comments</span></span>|<span data-ttu-id="873ec-134">의미</span><span class="sxs-lookup"><span data-stu-id="873ec-134">Meaning</span></span>|  
|--------------------------------------|-------------|  
|<span data-ttu-id="873ec-135">$Content (Trademark)</span><span class="sxs-lookup"><span data-stu-id="873ec-135">$Content (Trademark)</span></span>|<span data-ttu-id="873ec-136">응용 프로그램 작성자는 TextBlock 요소의 콘텐츠가 상표라는 것을 지역화 담당자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-136">The application author tells the localizer that the content in the TextBlock element is a trademark.</span></span>|  
|<span data-ttu-id="873ec-137">FontSize (Trademark font size)</span><span class="sxs-lookup"><span data-stu-id="873ec-137">FontSize (Trademark font size)</span></span>|<span data-ttu-id="873ec-138">응용 프로그램 작성자는 글꼴 크기 속성을 표준 상표 크기에 맞춰야 한다는 것을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-138">The application author indicates that the font size property should follow the standard trademark size.</span></span>|  
  
### <a name="localizability-attributes"></a><span data-ttu-id="873ec-139">지역화 가능성 특성</span><span class="sxs-lookup"><span data-stu-id="873ec-139">Localizability Attributes</span></span>  
 <span data-ttu-id="873ec-140">Localization.Attributes의 정보에는 대상 값 이름과 연관된 지역화 가능성 값이 쌍으로 된 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-140">The information in Localization.Attributes contains a list of pairs: the targeted value name and the associated localizability values.</span></span> <span data-ttu-id="873ec-141">대상 이름은 속성 이름 또는 특수한 $Content 이름일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-141">The target name can be a property name or the special $Content name.</span></span> <span data-ttu-id="873ec-142">속성 이름인 경우 대상 값은 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-142">If it is a property name, the targeted value is the value of the property.</span></span> <span data-ttu-id="873ec-143">$Content인 경우 대상 값은 요소의 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-143">If it is $Content, the target value is the content of the element.</span></span>  
  
 <span data-ttu-id="873ec-144">다음 세 가지 형식의 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-144">There are three types of attributes:</span></span>  
  
-   <span data-ttu-id="873ec-145">**Category**</span><span class="sxs-lookup"><span data-stu-id="873ec-145">**Category**.</span></span> <span data-ttu-id="873ec-146">지역화 담당자 도구에서 값을 수정할 수 있어야 하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-146">This specifies whether a value should be modifiable from a localizer tool.</span></span> <span data-ttu-id="873ec-147"><xref:System.Windows.LocalizabilityAttribute.Category%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="873ec-147">See <xref:System.Windows.LocalizabilityAttribute.Category%2A>.</span></span>  
  
-   <span data-ttu-id="873ec-148">**가독성**.</span><span class="sxs-lookup"><span data-stu-id="873ec-148">**Readability**.</span></span> <span data-ttu-id="873ec-149">지역화 담당자 도구에서 값을 읽고 표시해야 하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-149">This specifies whether a localizer tool should read (and display) a value.</span></span> <span data-ttu-id="873ec-150"><xref:System.Windows.LocalizabilityAttribute.Readability%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="873ec-150">See <xref:System.Windows.LocalizabilityAttribute.Readability%2A>.</span></span>  
  
-   <span data-ttu-id="873ec-151">**수정 가능성**.</span><span class="sxs-lookup"><span data-stu-id="873ec-151">**Modifiability**.</span></span> <span data-ttu-id="873ec-152">지역화 담당자 도구에서 값 수정을 허용하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-152">This specifies whether a localizer tool allows a value to be modified.</span></span> <span data-ttu-id="873ec-153"><xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="873ec-153">See <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>.</span></span>  
  
 <span data-ttu-id="873ec-154">이러한 특성은 공백으로 구분하여 임의의 순서로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-154">These attributes can be specified in any order delimited by a space.</span></span> <span data-ttu-id="873ec-155">중복된 특성이 지정된 경우 마지막 특성이 이전 특성을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-155">In case duplicate attributes are specified, the last attribute will override former ones.</span></span> <span data-ttu-id="873ec-156">예를 들어 Localization.Attributes = “Unmodifiable Modifiable”은 Modifiability를 마지막 값인 Modifiable로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-156">For example, Localization.Attributes = "Unmodifiable Modifiable" sets Modifiability to Modifiable because it is the last value.</span></span>  
  
 <span data-ttu-id="873ec-157">Modifiability 및 Readability는 이름만으로도 해당 의미를 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-157">Modifiability and Readability are self-explanatory.</span></span> <span data-ttu-id="873ec-158">Category 특성은 지역화 담당자가 텍스트를 번역할 때 도움이 되는 미리 정의된 범주를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-158">The Category attribute provides predefined categories that help the localizer when translating text.</span></span> <span data-ttu-id="873ec-159">Text, Label 및 Title과 같은 범주는 텍스트를 번역하는 방법에 대한 정보를 지역화 담당자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-159">Categories, such as, Text, Label, and Title give the localizer information about how to translate the text.</span></span> <span data-ttu-id="873ec-160">또한 None, Inherit, Ignore, NeverLocalize 등과 같은 특수한 범주도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-160">There are also special categories: None, Inherit, Ignore, and NeverLocalize.</span></span>  
  
 <span data-ttu-id="873ec-161">다음 표에서는 특수한 범주의 의미를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-161">The following table shows the meaning of the special categories.</span></span>  
  
|<span data-ttu-id="873ec-162">범주</span><span class="sxs-lookup"><span data-stu-id="873ec-162">Category</span></span>|<span data-ttu-id="873ec-163">의미</span><span class="sxs-lookup"><span data-stu-id="873ec-163">Meaning</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="873ec-164">없음</span><span class="sxs-lookup"><span data-stu-id="873ec-164">None</span></span>|<span data-ttu-id="873ec-165">대상 값에 정의된 범주가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-165">Targeted value has no defined category.</span></span>|  
|<span data-ttu-id="873ec-166">상속</span><span class="sxs-lookup"><span data-stu-id="873ec-166">Inherit</span></span>|<span data-ttu-id="873ec-167">대상 값은 부모로부터 해당 범주를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-167">Targeted value inherits its category from its parent.</span></span>|  
|<span data-ttu-id="873ec-168">무시</span><span class="sxs-lookup"><span data-stu-id="873ec-168">Ignore</span></span>|<span data-ttu-id="873ec-169">대상 값은 지역화 프로세스에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-169">Targeted value is ignored in the localization process.</span></span> <span data-ttu-id="873ec-170">Ignore는 현재 값에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-170">Ignore affects only the current value.</span></span> <span data-ttu-id="873ec-171">자식 노드에 영향을 주지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-171">It will not affect child nodes.</span></span>|  
|<span data-ttu-id="873ec-172">NeverLocalize</span><span class="sxs-lookup"><span data-stu-id="873ec-172">NeverLocalize</span></span>|<span data-ttu-id="873ec-173">현재 값을 지역화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-173">Current value cannot be localized.</span></span> <span data-ttu-id="873ec-174">이 범주는 요소의 자식에 의해 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-174">This category is inherited by the children of an element.</span></span>|  
  
<a name="Localization_Comments"></a>   
## <a name="localization-comments"></a><span data-ttu-id="873ec-175">지역화 주석</span><span class="sxs-lookup"><span data-stu-id="873ec-175">Localization Comments</span></span>  
 <span data-ttu-id="873ec-176">Localization.Comments에는 대상 값에 대한 자유 형식 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-176">Localization.Comments contains free-form strings concerning the targeted value.</span></span> <span data-ttu-id="873ec-177">응용 프로그램 개발자는 응용 프로그램 텍스트를 번역하는 방법에 대한 힌트를 지역화 담당자에게 제공하는 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-177">Application developers can add information to give localizers hints about how the applications text should be translated.</span></span> <span data-ttu-id="873ec-178">주석 형식은 “()”로 묶인 문자열일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-178">The format of the comments can be any string surrounded by "()".</span></span> <span data-ttu-id="873ec-179">문자를 이스케이프하려면 ‘\\’를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="873ec-179">Use '\\' to escape characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="873ec-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="873ec-180">See Also</span></span>  
 [<span data-ttu-id="873ec-181">WPF의 전역화</span><span class="sxs-lookup"><span data-stu-id="873ec-181">Globalization for WPF</span></span>](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [<span data-ttu-id="873ec-182">자동 레이아웃을 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="873ec-182">Use Automatic Layout to Create a Button</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)  
 [<span data-ttu-id="873ec-183">자동 레이아웃에 그리드 사용</span><span class="sxs-lookup"><span data-stu-id="873ec-183">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)  
 [<span data-ttu-id="873ec-184">응용 프로그램 지역화</span><span class="sxs-lookup"><span data-stu-id="873ec-184">Localize an Application</span></span>](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)
