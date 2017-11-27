---
title: Using Procedural Activities
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c391316959829c77d16dd87af51d9fe1915dc88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-procedural-activities"></a><span data-ttu-id="9b721-102">Using Procedural Activities</span><span class="sxs-lookup"><span data-stu-id="9b721-102">Using Procedural Activities</span></span>
<span data-ttu-id="9b721-103">이 샘플에서는 <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> 및 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 추측 게임을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-103">The sample uses the <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>, and <xref:System.Activities.Statements.WriteLine> activities to implement a guessing game.</span></span> <span data-ttu-id="9b721-104">이 추측 게임이 임의의 숫자를 선택하면 플레이어는 해당 숫자를 추측해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-104">The guessing game selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="9b721-105">플레이어의 추측이 틀리면 워크플로에서는 더 높은 숫자나 더 낮은 숫자를 추측하라는 힌트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-105">When the player submits an incorrect guess, the workflow provides a hint whether to guess higher or lower.</span></span> <span data-ttu-id="9b721-106">플레이어가 7회 미만의 시도에서 숫자를 맞추면 특별한 축하 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-106">If the player guesses the number in less than 7 attempts, a special congratulations is displayed to the user.</span></span>  
  
## <a name="custom-activities-in-this-sample"></a><span data-ttu-id="9b721-107">이 샘플의 사용자 지정 활동</span><span class="sxs-lookup"><span data-stu-id="9b721-107">Custom Activities in this Sample</span></span>  
  
### <a name="readline"></a><span data-ttu-id="9b721-108">ReadLine</span><span class="sxs-lookup"><span data-stu-id="9b721-108">ReadLine</span></span>  
 <span data-ttu-id="9b721-109">콘솔에서 텍스트 줄을 읽어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-109">Reads a line of text from the console.</span></span> <span data-ttu-id="9b721-110">이 활동은 <xref:System.Activities.NativeActivity> 클래스에서 파생된 것으로, 줄을 읽었을 때 콘솔 응용 프로그램에 의해 다시 시작되는 책갈피를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-110">This activity derives from the <xref:System.Activities.NativeActivity> class and creates a bookmark that is resumed by the console application when a line is read.</span></span>  
  
### <a name="promptint"></a><span data-ttu-id="9b721-111">PromptInt</span><span class="sxs-lookup"><span data-stu-id="9b721-111">PromptInt</span></span>  
 <span data-ttu-id="9b721-112">사용자에게 숫자를 입력하라는 메시지를 표시하고 콘솔 창에서 해당 숫자를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-112">Prompts the user to type in a number and then reads it from a console window.</span></span> <span data-ttu-id="9b721-113">이 활동은 <xref:System.Activities.Activity%601>에서 파생된 것으로, <xref:System.Activities.Statements.WriteLine> 및 `ReadLine` 활동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-113">The activity derives from <xref:System.Activities.Activity%601> and uses the <xref:System.Activities.Statements.WriteLine> and `ReadLine` activities.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="9b721-114">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="9b721-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="9b721-115">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 GuessingGame.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the GuessingGame.sln solution file.</span></span>  
  
2.  <span data-ttu-id="9b721-116">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="9b721-117">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9b721-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9b721-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9b721-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9b721-120">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="9b721-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9b721-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b721-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`  
  
## <a name="see-also"></a><span data-ttu-id="9b721-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b721-122">See Also</span></span>
