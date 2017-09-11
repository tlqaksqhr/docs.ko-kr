---
title: "프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
dev_langs:
- VB
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7e6a835f84f2e37f4f583bc16c24cf9bb28cc92a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="03705-102">프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="03705-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="03705-103">프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="03705-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="03705-104">이 때문에 XML IntelliSense를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03705-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="03705-105">프로젝트에 포함 하는 XML XSD (스키마 정의) 스키마에 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03705-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="03705-106">이 오류는 프로젝트에 대해 설정 된 기존 XSD 스키마를 사용 하 여 충돌 하는 XSD 스키마 (.xsd) 파일을 추가할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="03705-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="03705-107">**오류 ID:** BC36810</span><span class="sxs-lookup"><span data-stu-id="03705-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03705-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="03705-108">To correct this error</span></span>  
  
-   <span data-ttu-id="03705-109">경고를 두 번 클릭은 **오류 목록** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="03705-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="03705-110">Visual Basic 경고의 원인이 되는 XSD 파일의 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="03705-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="03705-111">XSD 스키마에서 오류를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03705-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="03705-112">필요한 모든 XSD 스키마 (.xsd) 파일은 프로젝트에 포함 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="03705-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="03705-113">클릭 해야 할 수도 **모든 파일 표시** 에 **프로젝트** .xsd를 메뉴에 파일 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="03705-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="03705-114">.Xsd 파일을 마우스 오른쪽 단추로 누른 **프로젝트에 포함** 를 프로젝트에 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="03705-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="03705-115">XML to Schema 마법사를 사용 하는 동일한 소스에서 스키마를 한 번 이상 유추한 하는 경우이 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03705-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="03705-116">이 경우 프로젝트에서 기존 XSD 스키마 파일을 제거할 수 있습니다 스키마 항목 템플릿에 새 XML 추가 하 고 XML을 입력 스키마 마법사, 적용 가능한 모든 XML 소스와 프로젝트에 대 한 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="03705-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="03705-117">오류가 발생 하지는 XSD 스키마에서 식별 되 면 XML 컴파일러는 자세한 오류 메시지를 제공할 수 있는 충분 한 정보가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03705-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="03705-118">.Xsd 파일에 대 한 XML 네임 스페이스에에서 포함 되도록 프로젝트 일치를 사용 하 여 Visual Studio에서 설정 된 XML 스키마에 대해 식별 된 XML 네임 스페이스를 확인 하는 경우 자세한 오류 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03705-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03705-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03705-119">See Also</span></span>  
 <span data-ttu-id="03705-120">[오류 목록 창](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window) </span><span class="sxs-lookup"><span data-stu-id="03705-120">[Error List Window](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window) </span></span>  
<span data-ttu-id="03705-121"> [Visual Basic의 XML IntelliSense](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md) </span><span class="sxs-lookup"><span data-stu-id="03705-121"> [XML IntelliSense in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md) </span></span>  
<span data-ttu-id="03705-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="03705-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
