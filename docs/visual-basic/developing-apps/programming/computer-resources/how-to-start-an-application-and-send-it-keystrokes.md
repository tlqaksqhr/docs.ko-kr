---
title: "방법: 응용 프로그램 시작 및 키 입력 보내기(Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: 15
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 142db417b6b61724ad80bd3f8e5083dd420b3aeb
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="a7ccb-102">방법: 응용 프로그램 시작 및 키 입력 보내기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7ccb-102">How to: Start an Application and Send it Keystrokes (Visual Basic)</span></span>
<span data-ttu-id="a7ccb-103">이 예제에서는 `Shell` 함수를 사용하여 계산기 응용 프로그램을 시작한 다음 `My.Computer.Keyboard.SendKeys` 메서드를 통해 키 입력을 전송하여 두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ccb-103">This example uses the `Shell` function to start the calculator application and then multiplies two numbers by sending keystrokes using the `My.Computer.Keyboard.SendKeys` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7ccb-104">예제</span><span class="sxs-lookup"><span data-stu-id="a7ccb-104">Example</span></span>  
 <span data-ttu-id="a7ccb-105">[!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7ccb-105">[!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a7ccb-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a7ccb-106">Robust Programming</span></span>  
 <span data-ttu-id="a7ccb-107">요청된 프로세스 식별자를 가진 응용 프로그램을 찾을 수 없는 경우 <xref:System.ArgumentException> 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ccb-107">A <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a7ccb-108">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="a7ccb-108">.NET Framework Security</span></span>  
 <span data-ttu-id="a7ccb-109">`Shell` 함수에 대한 호출은 완전 신뢰가 필요합니다(<xref:System.Security.SecurityException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="a7ccb-109">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ccb-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7ccb-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>

