---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f3c101ad13df9b99a2d872bac8783baed8b4b9a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="getcustomui"></a><span data-ttu-id="8c807-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="8c807-102">GetCustomUI</span></span>
<span data-ttu-id="8c807-103">구현 된 경우에 호스트에서 사용자 지정 진행률과 오류 메시지를 가져오려는 PresentationHost.exe에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c807-104">구문</span><span class="sxs-lookup"><span data-stu-id="8c807-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c807-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c807-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="8c807-106">[out] 호스트에서 제공한 진행률 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="8c807-107">[out] 대부분의 사용자 인터페이스를 클래스의 이름은 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 파일 <xref:System.Windows.Controls.Page> 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="8c807-108">이 클래스에 지정 된 어셈블리에 있는 `pwzProgressAssemblyName`합니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="8c807-109">[out] 호스트에서 제공한 오류 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="8c807-110">[out] 호스트에서 제공한 오류 사용자 인 클래스의 이름 인터페이스, 가급적와 XAML 파일 <xref:System.Windows.Controls.Page> 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="8c807-111">이 클래스에 지정 된 어셈블리에 있는 `pwzErrorAssemblyName`합니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8c807-112">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="8c807-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="8c807-113">HRESULT: 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c807-114">설명</span><span class="sxs-lookup"><span data-stu-id="8c807-114">Remarks</span></span>  
 <span data-ttu-id="8c807-115">호스트 응용 프로그램 PresentationHost.exe의 기본 사용자 인터페이스를 준수 하지 않는 특정 테마가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="8c807-116">이 경우 호스트 응용 프로그램을 구현할 수 [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) 돌아가려면 진행률과 오류 사용자 인터페이스 PresentationHost.exe 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-116">If this is the case, the host application can implement [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="8c807-117">PresentationHost.exe 항상 호출 됩니다 [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) 해당 기본 사용자 인터페이스를 사용 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="8c807-117">PresentationHost.exe will always call [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="8c807-118">이 함수는 PresentationHost의 초기화 동안 한 번 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c807-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c807-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c807-119">See Also</span></span>  
 [<span data-ttu-id="8c807-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="8c807-120">IWpfHostSupport</span></span>](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
