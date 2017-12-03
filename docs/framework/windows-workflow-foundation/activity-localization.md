---
title: "활동 지역화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18856fe11d95d5b54bc580b83eae35badb4d86e6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="activity-localization"></a><span data-ttu-id="d2d30-102">활동 지역화</span><span class="sxs-lookup"><span data-stu-id="d2d30-102">Activity Localization</span></span>
<span data-ttu-id="d2d30-103">워크플로 응용 프로그램 및 구성 요소가 다른 문화권과 언어로 지역화될 가능성이 있는 경우 다시 컴파일하지 않고 지역화할 수 있도록 리소스 문자열을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-103">When workflow applications and components have the potential to be localized into other cultures and languages, resource strings should be used so that they can be localized without recompiling.</span></span>  
  
## <a name="activity-localization"></a><span data-ttu-id="d2d30-104">활동 지역화</span><span class="sxs-lookup"><span data-stu-id="d2d30-104">Activity Localization</span></span>  
 <span data-ttu-id="d2d30-105">지역화해야 하는(다른 언어와 문화권에 대해 다른 버전으로 릴리스해야 하는) 모든 응용 프로그램에서 사용자에게 표시되는 문자열은 코드에 직접 넣지 말고 리소스 파일에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-105">As with all applications that must be localized (released in different versions for different languages and cultures), any strings that are displayed to the user should not be put directly in code, but rather stored in a resource file.</span></span> <span data-ttu-id="d2d30-106">문자열을 통해 액세스할 수 있습니다 <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-106">The strings can then be accessed through <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span></span> <span data-ttu-id="d2d30-107">여러 언어로 배포되는 구성 요소를 개발하는 경우 활동 유효성 검사 메시지, 사용자 정의 추적 데이터, 추적 메시지 및 오류 메시지에도 리소스 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-107">If you are developing a component that is distributed in several languages, you also want to use resource strings for activity validation messages, user-defined tracking data, tracing messages, and error messages as well.</span></span>  
  
 <span data-ttu-id="d2d30-108">다음 연습에서는 리소스 파일을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-108">The following exercise demonstrates how to use a resource file.</span></span>  
  
#### <a name="using-resource-files-for-localized-strings"></a><span data-ttu-id="d2d30-109">지역화되는 문자열에 리소스 파일 사용</span><span class="sxs-lookup"><span data-stu-id="d2d30-109">Using resource files for localized strings</span></span>  
  
1.  <span data-ttu-id="d2d30-110">[!INCLUDE[vs2010](../../../includes/vs2010-md.md)]에서 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **추가 중...** , **새 항목...** .</span><span class="sxs-lookup"><span data-stu-id="d2d30-110">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], right-click your project in **Solution Explorer** and select **Add…**, **New Item…**.</span></span>  
  
2.  <span data-ttu-id="d2d30-111">선택 **리소스 파일** errorresources.resx로 지정 된 파일 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-111">Select **Resources File** and name the file ErrorResources.resx.</span></span> <span data-ttu-id="d2d30-112">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-112">Click **Add**.</span></span>  
  
3.  <span data-ttu-id="d2d30-113">리소스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-113">Open the resource file.</span></span> <span data-ttu-id="d2d30-114">상태에서 새 항목 추가 **이름** 을 errorstring으로 지정 및 **값** "활동 올바르지 않습니다."의</span><span class="sxs-lookup"><span data-stu-id="d2d30-114">Add a new entry with a **Name** of ErrorString and a **Value** of "The activity is not valid."</span></span>  
  
4.  <span data-ttu-id="d2d30-115">클래스에 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-115">Add the following `using` statements to your class.</span></span>  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
    ```  
  
5.  <span data-ttu-id="d2d30-116">프로젝트에서 리소스 관리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-116">Create a resource manager in your project.</span></span>  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
    ```  
  
6.  <span data-ttu-id="d2d30-117">필요한 경우 리소스 관리자에서 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-117">Get the string from the resource manager where it is required.</span></span>  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
    ```  
  
 <span data-ttu-id="d2d30-118">다음 코드 샘플에서는 <xref:System.Activities.Activity.CacheMetadata%2A> 메서드에서 지역화되는 문자열을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2d30-118">The following code sample demonstrates how to utilize localized strings in the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span>  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```
