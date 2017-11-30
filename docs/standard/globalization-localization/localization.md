---
title: "지역화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a><span data-ttu-id="35a97-102">지역화</span><span class="sxs-lookup"><span data-stu-id="35a97-102">Localization</span></span>
<span data-ttu-id="35a97-103">지역화는 응용 프로그램이 지 원하는 각 문화권에 대 한 지역화 된 버전에는 응용 프로그램의 리소스를 변환 하는 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="35a97-104">완료 한 후에 지역화 단계를 진행 해야는 [지역화 가능성 검토](../../../docs/standard/globalization-localization/localizability-review.md) 전역화 된 응용 프로그램 지역화 될 준비가 되었는지 확인 하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>  
  
 <span data-ttu-id="35a97-105">지역화를 위해 준비 하는 응용 프로그램은 두 개의 개념적 블록, 모든 사용자 인터페이스 요소를 포함 하는 블록 및 실행 코드가 포함 된 블록으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-105">An application that is ready for localization is separated into two conceptual blocks, a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="35a97-106">사용자 인터페이스 블록 예: 문자열, 오류 메시지, 대화 상자, 메뉴, 중립 문화권에 대해 포함 된 개체 리소스를 지역화할 수 있는 사용자 인터페이스 요소에만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="35a97-107">코드 블록에는 모든 지원 되는 문화권에서 사용할 응용 프로그램 코드에만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="35a97-108">공용 언어 런타임 리소스와에서 응용 프로그램의 실행 코드를 구분 하는 위성 어셈블리 리소스 모델을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="35a97-109">이 모델을 구현 하는 방법에 대 한 자세한 내용은 참조 [데스크톱 응용 프로그램의 리소스](../../../docs/framework/resources/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-109">For more information about implementing this model, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="35a97-110">각 지역화 된 버전의 응용 프로그램에 대 한 지역화 된 사용자 인터페이스 블록의 대상 문화권에 대 한 적절 한 언어로 번역을 포함 하는 새 위성 어셈블리를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="35a97-111">모든 문화권에 대 한 코드 블록 동일 하 게 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="35a97-112">조합 된 코드 블록이 사용자 인터페이스 블록의 지역화 된 버전의 응용 프로그램의 지역화 된 버전을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>  
  
 <span data-ttu-id="35a97-113">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Windows Forms 리소스 편집기 (Winres.exe) 신속 하 게 대상 문화권에 대 한 Windows Forms를 지역화할 수 있도록 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-113">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="35a97-114">이 도구를 사용 하는 방법에 대 한 정보를 참조 하십시오. [Winres.exe (Windows Forms 리소스 편집기)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35a97-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a97-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35a97-115">See Also</span></span>  
 [<span data-ttu-id="35a97-116">전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="35a97-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="35a97-117">지역화 가능성 검토</span><span class="sxs-lookup"><span data-stu-id="35a97-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 [<span data-ttu-id="35a97-118">전역화</span><span class="sxs-lookup"><span data-stu-id="35a97-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="35a97-119">데스크톱 앱의 리소스</span><span class="sxs-lookup"><span data-stu-id="35a97-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
