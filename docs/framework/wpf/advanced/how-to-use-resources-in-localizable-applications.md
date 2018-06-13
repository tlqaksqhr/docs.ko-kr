---
title: '방법: 지역화할 수 있는 응용 프로그램에서 리소스 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 82a24feb4008b6cfd7c1751c6449c0d8515ffe87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544705"
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="b2682-102">방법: 지역화할 수 있는 응용 프로그램에서 리소스 사용</span><span class="sxs-lookup"><span data-stu-id="b2682-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="b2682-103">지역화 맞게 것을 의미 한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 다른 culture입니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="b2682-104">이렇게 하려면 제목, 캡션, 목록 상자 항목 등과 같은 텍스트를 번역해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="b2682-105">번역을 쉽게 하기 위해 번역할 항목이 리소스 파일로 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="b2682-106">참조 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) 지역화에 리소스 파일을 만드는 방법에 대 한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-106">See [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="b2682-107">확인 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지역화할 수 있는 리소스 어셈블리를 지역화할 수 있는 모든 리소스를 만드는 데 필요한 개발자 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="b2682-108">다른 언어로 지역화 된 리소스 어셈블리 및 리소스 관리를 사용 하는 코드 숨김 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] 를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-108">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="b2682-109">에 필요한 파일 중 하나는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 프로젝트 파일 (.proj)입니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="b2682-110">응용 프로그램에서 사용하는 모든 리소스는 프로젝트 파일에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="b2682-111">다음 코드 예제에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2682-112">예제</span><span class="sxs-lookup"><span data-stu-id="b2682-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="b2682-113">인스턴스화할 리소스에서 응용 프로그램을 사용 하려면 <xref:System.Resources.ResourceManager> 하 고 사용 하려는 리소스를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="b2682-114">다음에서는 이 작업을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2682-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
