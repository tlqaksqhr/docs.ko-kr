---
title: "방법: 다른 워크플로 서비스를 호출하는 워크플로 서비스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0a3b9f77445e8629fb67d099c6d7944044897fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a><span data-ttu-id="a7164-102">방법: 다른 워크플로 서비스를 호출하는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="a7164-102">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>
<span data-ttu-id="a7164-103">워크플로 서비스에서 다른 워크플로 서비스의 정보를 얻어야 하는 경우가 가끔 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-103">It is sometimes necessary for a workflow service to obtain information from another workflow service.</span></span>  <span data-ttu-id="a7164-104">이 항목에서는 워크플로 서비스 간에 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-104">This topic demonstrates how to call one workflow service from another.</span></span> <span data-ttu-id="a7164-105">이 항목에서는 두 개의 워크플로 서비스를 만듭니다. 하나는 입력 문자열의 방향을 반대로 바꾸는 메서드가 있는 서비스이고, 다른 하나는 첫 번째 서비스를 사용하는 문자열의 방향을 반대로 바꾼 후 입력 문자열을 대문자로 변환하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-105">In this topic, we’ll create two workflow services; one that has a method that reverses the input string, and another that converts the input string to uppercase after reversing the string that uses the first service.</span></span>  
  
### <a name="to-create-the-reverser-workflow-service"></a><span data-ttu-id="a7164-106">Reverser 워크플로 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a7164-106">To create the Reverser workflow service</span></span>  
  
1.  <span data-ttu-id="a7164-107">관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-107">Run [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] as an administrator.</span></span>  
  
2.  <span data-ttu-id="a7164-108">선택 **파일**, **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-108">Select **File**, **New Project**.</span></span> <span data-ttu-id="a7164-109">아래는 **워크플로** 에서 노드는 **설치 된 템플릿** 창 선택 **WCF 워크플로 서비스 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-109">Under the **Workflow** node in the **Installed Templates** pane, select **WCF Workflow Service Application**.</span></span> <span data-ttu-id="a7164-110">솔루션 이름을 `NestedServices` 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-110">Name the solution `NestedServices` and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="a7164-111">아래 **서버**, 다음 사항을 확인 **로컬 IIS 웹 서버 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-111">Under **Servers**, make sure that **Use Local IIS Web Server** is selected.</span></span> <span data-ttu-id="a7164-112">클릭 **가상 디렉터리 만들기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-112">Click **Create Virtual Directory**.</span></span> <span data-ttu-id="a7164-113">클릭 **확인** 에 가상 디렉터리가 성공적으로 만들었다는 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-113">Click **OK** in the dialog box stating that the virtual directory was successfully created.</span></span>  
  
4.  <span data-ttu-id="a7164-114">솔루션 탐색기에서 Service1.xamlx의 이름을 바꿀 `StringReverserService.xamlx`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-114">In Solution Explorer, rename Service1.xamlx to `StringReverserService.xamlx`.</span></span>  
  
5.  <span data-ttu-id="a7164-115">에 **프로젝트 속성** 새 프로젝트에 대 한 페이지는 **웹** 탭 합니다. 설정의 **시작 작업** 를 **특정 페이지**를 하 고 StringReverserService.xamlx를 시작 하려면 페이지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-115">On the **Project Properties** page for the new project, click the **Web** tab. Set the **Start Action** to **Specific Page**, and select StringReverserService.xamlx as the page to start.</span></span>  
  
6.  <span data-ttu-id="a7164-116">디자이너에서 StringReverserService.xamlx를 열고 기존 `ReceiveRequest` 및 `SendReply` 활동을 삭제한 다음 `ReceiveAndSendReply` 활동을 기존 시퀀스 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-116">Open StringReverserService.xamlx in the designer and delete the existing `ReceiveRequest` and `SendReply` activities, and then drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="a7164-117">설정의 **OperationName** 을 reversestring으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-117">Set the **OperationName** to ReverseString.</span></span>  
  
    2.  <span data-ttu-id="a7164-118">설정의 **ServiceContractName** 을 ireversestring으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-118">Set the **ServiceContractName** to IReverseString.</span></span>  
  
    3.  <span data-ttu-id="a7164-119">선택 된 **CanCreateInstance** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-119">Select the **CanCreateInstance** check box.</span></span>  
  
7.  <span data-ttu-id="a7164-120">선택 된 **SequentialService** 활동과 클릭 한 다음는 **변수** 디자이너의 아래쪽에 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-120">Select the **SequentialService** activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="a7164-121">String 형식의 StringToReverse 및 ReversedStringToReturn이라는 새로운 두 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-121">Create two new variables named StringToReverse and ReversedStringToReturn of type String.</span></span>  
  
8.  <span data-ttu-id="a7164-122">클릭는 **정의** 연결에 **수신** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-122">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="a7164-123">클릭는 **매개 변수**, 고 StringToReverse에 할당 되는 String 형식의 InputString 이라는 매개 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-123">Click the  **Parameters**, and create a parameter named InputString of type String that assigns to StringToReverse.</span></span>  
  
9. <span data-ttu-id="a7164-124">클릭는 **정의** 연결에 **SendReplyToReceive** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-124">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="a7164-125">클릭는 **매개 변수**, String 형식의 ReversedStringToReturn에 할당 된 ReversedString 이라는 매개 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-125">Click the **Parameters**, and create a parameter named ReversedString of type String, assigned to ReversedStringToReturn.</span></span>  
  
10. <span data-ttu-id="a7164-126">서비스의 논리를 구현하려면 프로젝트에 StringLibrary라는 새 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-126">To implement the logic for the service, create a new class in the project called StringLibrary.</span></span>  <span data-ttu-id="a7164-127">클래스 정의를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-127">Replace the class definition with the following code.</span></span>  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. <span data-ttu-id="a7164-128">입력에 ReverseString 메서드를 호출 하려면 끌어는 **InvokeMethod** 도구 상자의 활동 사이의 공간에는 **수신** 및 **SendReply** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-128">To call the ReverseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="a7164-129">활동의 속성을 다음과 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-129">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="a7164-130">**MethodName**: reversestring으로</span><span class="sxs-lookup"><span data-stu-id="a7164-130">**MethodName**: ReverseString</span></span>  
  
    2.  <span data-ttu-id="a7164-131">**결과**: ReversedStringToReturn</span><span class="sxs-lookup"><span data-stu-id="a7164-131">**Result**: ReversedStringToReturn</span></span>  
  
    3.  <span data-ttu-id="a7164-132">**매개 변수**: 인 새 매개 변수 만들기는 **방향** 이 In는 **형식** 문자열의 및 **값** StringToReverse의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-132">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToReverse.</span></span>  
  
    4.  <span data-ttu-id="a7164-133">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="a7164-133">**TargetType**: NestedServices.StringLibrary</span></span>  
  
12. <span data-ttu-id="a7164-134">F5 키를 눌러 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-134">Test the service by pressing F5.</span></span> <span data-ttu-id="a7164-135">WCF 테스트 클라이언트가 표시되면 ReverseString() 메서드를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-135">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="a7164-136">요청 창에 입력 `Sample` InputString 매개 변수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-136">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="a7164-137">클릭 **호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-137">Click **Invoke**.</span></span> <span data-ttu-id="a7164-138">그러면 서비스에서 "elpmaS"를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-138">The service should return "elpmaS".</span></span>  
  
### <a name="to-create-the-uppercaser-workflow-service"></a><span data-ttu-id="a7164-139">UpperCaser 워크플로 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a7164-139">To create the UpperCaser workflow service</span></span>  
  
1.  <span data-ttu-id="a7164-140">NestedServices 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가**, **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-140">Right-click the NestedServices project and select **Add**, **New Item**.</span></span> <span data-ttu-id="a7164-141">에 **워크플로** 노드를 **WCF 워크플로 서비스**, 새 서비스 이름을 `UpperCaserService`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-141">In the **Workflow** node, select **WCF Workflow Service**, and name the new service `UpperCaserService`.</span></span> <span data-ttu-id="a7164-142">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-142">Click **Add**.</span></span> <span data-ttu-id="a7164-143">그러면 UpperCaserService.xamlx라는 새 워크플로 서비스가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-143">This should add a new workflow service called UpperCaserService.xamlx to the project.</span></span>  
  
2.  <span data-ttu-id="a7164-144">디자이너에서 UpperCaserService.xamlx를 열고 기존 삭제 **ReceiveRequest** 및 `SendReply` 활동과 끌어서는 `ReceiveAndSendReply` 활동을 기존 시퀀스 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-144">Open UpperCaserService.xamlx in the designer and delete the existing **ReceiveRequest** and `SendReply` activities, and drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="a7164-145">설정의 **OperationName** 을 uppercasestring으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-145">Set the **OperationName** to UpperCaseString.</span></span>  
  
    2.  <span data-ttu-id="a7164-146">설정의 **ServiceContractName** 을 iuppercasestring으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-146">Set the **ServiceContractName** to IUpperCaseString.</span></span>  
  
    3.  <span data-ttu-id="a7164-147">선택 된 **CanCreateInstance** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-147">Select the **CanCreateInstance** check box.</span></span>  
  
3.  <span data-ttu-id="a7164-148">SequentialService 활동을 선택한 다음 클릭는 **변수** 디자이너의 아래쪽에 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-148">Select the SequentialService activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="a7164-149">String 형식의 StringToUpper, StringToReverse 및 StringToReturn이라는 세 개의 새로운 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-149">Create three new variables named StringToUpper, StringToReverse, and StringToReturn of type String.</span></span>  
  
4.  <span data-ttu-id="a7164-150">클릭는 **정의** 연결에 **수신** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-150">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="a7164-151">클릭는 **매개 변수**, 고 StringToUpper에 할당 되는 String 형식의 InputString 이라는 매개 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-151">Click the **Parameters**, and create a parameter named InputString of type String that assigns to StringToUpper.</span></span>  
  
5.  <span data-ttu-id="a7164-152">클릭는 **정의** 연결에 **SendReplyToReceive** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-152">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="a7164-153">클릭는 **매개 변수**, String 형식의 StringToReturn에 할당 된 ModifiedString 이라는 매개 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-153">Click the **Parameters**, and create a parameter named ModifiedString of type String, assigned to StringToReturn.</span></span>  
  
6.  <span data-ttu-id="a7164-154">서비스의 논리를 구현하려면 다음 코드를 사용하여 StringLibrary 클래스에 새 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-154">To implement the logic for the service, create a new method in the StringLibrary class using the following code.</span></span>  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  <span data-ttu-id="a7164-155">입력에 UpperCaseString 메서드를 호출 하려면 끌어는 **InvokeMethod** 도구 상자의 활동 사이의 공간에는 **수신** 및 **SendReply** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-155">To call the UpperCaseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="a7164-156">활동의 속성을 다음과 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-156">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="a7164-157">**MethodName**: uppercasestring으로</span><span class="sxs-lookup"><span data-stu-id="a7164-157">**MethodName**: UpperCaseString</span></span>  
  
    2.  <span data-ttu-id="a7164-158">**결과**: StringToReverse</span><span class="sxs-lookup"><span data-stu-id="a7164-158">**Result**: StringToReverse</span></span>  
  
    3.  <span data-ttu-id="a7164-159">**매개 변수**: 인 새 매개 변수 만들기는 **방향** 이 In는 **형식** 문자열의 및 **값** 이 StringToUpper 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-159">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToUpper.</span></span>  
  
    4.  <span data-ttu-id="a7164-160">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="a7164-160">**TargetType**: NestedServices.StringLibrary</span></span>  
  
8.  <span data-ttu-id="a7164-161">이제 수정된 문자열에 대해 첫 번째 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-161">We’ll now call the first service on the modified string.</span></span> <span data-ttu-id="a7164-162">프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **서비스 참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-162">Right-click the project and select **Add Service Reference**.</span></span> <span data-ttu-id="a7164-163">http://localhost/NestedServices/StringReverserService.xamlx에 있는 서비스에 대한 서비스 참조를 추가하고 첫 번째 서비스에 액세스하는 사용자 지정 활동을 만드는 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-163">Add a service reference to the service at http://localhost/NestedServices/StringReverserService.xamlx and build the project to create a custom activity to access the first Web service.</span></span>  
  
9. <span data-ttu-id="a7164-164">끌어 새 활동의 인스턴스는 워크플로 간에 **InvokeMethod** 활동 및 **SendReplyToReceive** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-164">Drag an instance of the new activity onto the workflow, between the **InvokeMethod** activity and the **SendReplyToReceive** activities.</span></span> <span data-ttu-id="a7164-165">새 활동의 InputString 속성에 StringToReverse 변수를 할당하고 StringToReturn 속성에 StringToReturn 변수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-165">Assign the variable StringToReverse to the InputString property of the new activity, and the variable StringToReturn to the StringToReturn property.</span></span>  
  
10. <span data-ttu-id="a7164-166">NestedServices 프로젝트에 대 한 속성 페이지를 열고 변경는 **특정 페이지** 에 **웹** UpperCaserService.xamlx 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-166">Open the Properties page for the NestedServices project, and change the **Specific Page** in the **Web** tab to UpperCaserService.xamlx.</span></span>  
  
11. <span data-ttu-id="a7164-167">F5 키를 눌러 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-167">Test the service by pressing F5.</span></span> <span data-ttu-id="a7164-168">WCF 테스트 클라이언트가 표시되면 ReverseString() 메서드를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-168">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="a7164-169">요청 창에 입력 `Sample` InputString 매개 변수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-169">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="a7164-170">클릭 **호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-170">Click **Invoke**.</span></span> <span data-ttu-id="a7164-171">그러면 서비스에서 "ELPMAS"를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-171">The service should return "ELPMAS".</span></span>  
  
### <a name="to-create-a-client-to-call-the-services"></a><span data-ttu-id="a7164-172">서비스를 호출할 클라이언트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a7164-172">To create a client to call the services</span></span>  
  
1.  <span data-ttu-id="a7164-173">솔루션에 Client라는 새 콘솔 응용 프로그램 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-173">Add a new Console application project called Client to the solution.</span></span>  
  
2.  <span data-ttu-id="a7164-174">클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **서비스 참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-174">Right-click the Client project and select **Add Service Reference**.</span></span> <span data-ttu-id="a7164-175">표시 되는 창에서 클릭 **Discover**합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-175">In the window that appears, click **Discover**.</span></span> <span data-ttu-id="a7164-176">StringReverserService.xamlx를 선택하고 네임스페이스로 ReverseService를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-176">Select StringReverserService.xamlx, and enter ReverseService as the namespace.</span></span>  <span data-ttu-id="a7164-177">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-177">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="a7164-178">Program.cs의 Main 메서드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a7164-178">Replace the Main method in Program.cs with the following code.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```
