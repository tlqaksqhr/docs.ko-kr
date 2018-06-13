---
title: My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 421995684201ec48d5e8aff9b0ed7640efd1e4b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582664"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="343b4-102">My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="343b4-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="343b4-103">[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) 및 [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) 개체 폼, 데이터 원본 및 응용 프로그램에서 사용 하는 XML 웹 서비스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="343b4-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="343b4-104">컬렉션을 제공 하 여이 수행 *인스턴스를 기본* 이러한 각 개체의 합니다.</span><span class="sxs-lookup"><span data-stu-id="343b4-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="343b4-105">기본 인스턴스</span><span class="sxs-lookup"><span data-stu-id="343b4-105">Default Instances</span></span>  
 <span data-ttu-id="343b4-106">기본 인스턴스 수 하지 않아도 런타임에서 제공 하는 클래스의 인스턴스가 선언 되었고 사용 하 여 인스턴스화될는 `Dim` 및 `New` 문.</span><span class="sxs-lookup"><span data-stu-id="343b4-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="343b4-107">다음 예제에서는 방법을 있습니다 선언 하 고의 인스턴스를 인스턴스화할는 <xref:System.Windows.Forms.Form> 라는 클래스 `Form1`, 어떻게 현재 위치는이 기본 인스턴스를 가져올 수 및 <xref:System.Windows.Forms.Form> 클래스를 통해 `My.Forms`합니다.</span><span class="sxs-lookup"><span data-stu-id="343b4-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 <span data-ttu-id="343b4-108">`My.Forms` 의 기본 인스턴스 컬렉션을 반환 하는 개체 마다 `Form` 프로젝트에 있는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="343b4-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="343b4-109">마찬가지로, `My.WebServices` 응용 프로그램에 대 한 참조를 만든 모든 웹 서비스에 대 한 프록시 클래스의 기본 인스턴스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="343b4-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="343b4-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="343b4-110">See Also</span></span>  
 [<span data-ttu-id="343b4-111">My.Forms 개체</span><span class="sxs-lookup"><span data-stu-id="343b4-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [<span data-ttu-id="343b4-112">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="343b4-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [<span data-ttu-id="343b4-113">My가 프로젝트 형식에 의존하는 방식</span><span class="sxs-lookup"><span data-stu-id="343b4-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
