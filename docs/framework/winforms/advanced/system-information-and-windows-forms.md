---
title: "시스템 정보 및 Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- domain names [Windows Forms], retrieving
- SystemInformation class [Windows Forms]
- user names [Windows Forms], retrieving
- system information [Windows Forms]
ms.assetid: 30cf43a3-8cb2-4ff3-862b-6c34576616a8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6657556ffb49c19e6ffc3ef5462de341a93112b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="system-information-and-windows-forms"></a><span data-ttu-id="599df-102">시스템 정보 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="599df-102">System Information and Windows Forms</span></span>
<span data-ttu-id="599df-103">경우에 따라 코드에서 결정을 내리기 위해서는 응용 프로그램에서 실행 되는 컴퓨터에 대 한 정보를 수집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="599df-103">Sometimes it is necessary to gather information about the computer that your application is running on in order to make decisions in your code.</span></span> <span data-ttu-id="599df-104">예를 들어만 특정 네트워크 도메인;에 연결 하는 경우에 적용할 수 있는 함수를 할 수 있습니다. 이 경우 도메인을 확인 하 고 도메인 스위치가 없을 경우 함수를 사용 하지 않도록 설정 하는 방법에 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="599df-104">For example, you might have a function that is only applicable when connected to a particular network domain; in this case you would need a way to determine the domain and disable the function if the domain is not present.</span></span>  
  
 <span data-ttu-id="599df-105">Windows Forms 응용 프로그램에서 사용할 수는 <xref:System.Windows.Forms.SystemInformation> 실행 시 다양 한 컴퓨터에 대 한 작업을 확인 하려면 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="599df-105">Windows Forms applications can use the <xref:System.Windows.Forms.SystemInformation> class to determine a number of things about a computer at run time.</span></span> <span data-ttu-id="599df-106">다음 예제는 <xref:System.Windows.Forms.SystemInformation> 검색할 클래스는 <xref:System.Windows.Forms.SystemInformation.UserName%2A> 및 <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span><span class="sxs-lookup"><span data-stu-id="599df-106">The following example demonstrates using the <xref:System.Windows.Forms.SystemInformation> class to retrieve the <xref:System.Windows.Forms.SystemInformation.UserName%2A> and <xref:System.Windows.Forms.SystemInformation.UserDomainName%2A>:</span></span>  
  
```vb  
Dim User As String = Windows.Forms.SystemInformation.UserName  
Dim Domain As String = Windows.Forms.SystemInformation.UserDomainName  
  
MessageBox.Show("Good morning " & User & ". You are connected to " _  
& Domain)  
```  
  
```csharp  
string User = SystemInformation.UserName;  
string Domain = SystemInformation.UserDomainName;  
  
MessageBox.Show("Good morning " + User + ". You are connected to " _  
+ Domain)  
```  
  
 <span data-ttu-id="599df-107">모든 멤버는 <xref:System.Windows.Forms.SystemInformation> 클래스는 읽기 전용, 사용자의 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="599df-107">All members of the <xref:System.Windows.Forms.SystemInformation> class are read-only; you cannot modify a user's settings.</span></span> <span data-ttu-id="599df-108">컴퓨터에 연결 하는 모니터의 수는 모든 정보를 반환 하는 클래스의 100 개 이상의 멤버가 (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) Windows 탐색기에서 아이콘의 간격으로 (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> 및 <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span><span class="sxs-lookup"><span data-stu-id="599df-108">There are over 100 members of the class, returning information on everything from the number of monitors attached to the computer (<xref:System.Windows.Forms.SystemInformation.MonitorCount%2A>) to the spacing of icons in Windows Explorer (<xref:System.Windows.Forms.SystemInformation.IconHorizontalSpacing%2A> and <xref:System.Windows.Forms.SystemInformation.IconVerticalSpacing%2A>).</span></span>  
  
 <span data-ttu-id="599df-109">보다 유용한 멤버 중 일부는 <xref:System.Windows.Forms.SystemInformation> 클래스 포함 <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, 및 <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="599df-109">Some of the more useful members of the <xref:System.Windows.Forms.SystemInformation> class include <xref:System.Windows.Forms.SystemInformation.ComputerName%2A>, <xref:System.Windows.Forms.SystemInformation.DbcsEnabled%2A>, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>, and <xref:System.Windows.Forms.SystemInformation.TerminalServerSession%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="599df-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="599df-110">See Also</span></span>  
 <xref:System.Windows.Forms.SystemInformation>  
 [<span data-ttu-id="599df-111">Windows Forms의 전원 관리</span><span class="sxs-lookup"><span data-stu-id="599df-111">Power Management in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/power-management-in-windows-forms.md)
