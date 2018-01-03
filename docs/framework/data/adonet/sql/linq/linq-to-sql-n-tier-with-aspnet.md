---
title: "ASP.NET을 사용하는 LINQ to SQL N 계층"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 477af694874ada4ae24fda0f1dbfac824a5aadbe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a><span data-ttu-id="dc9dc-102">ASP.NET을 사용하는 LINQ to SQL N 계층</span><span class="sxs-lookup"><span data-stu-id="dc9dc-102">LINQ to SQL N-Tier with ASP.NET</span></span>
<span data-ttu-id="dc9dc-103">[!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] 을 사용하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]응용 프로그램에서는 <xref:System.Web.UI.WebControls.LinqDataSource> 웹 서버 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9dc-103">In [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the <xref:System.Web.UI.WebControls.LinqDataSource> Web server control.</span></span> <span data-ttu-id="dc9dc-104">이 컨트롤은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대해 쿼리하는 데 필요한 대부분의 논리를 처리하고, 데이터를 브라우저에 전달하고 검색하며, 최종적으로 데이터베이스를 업데이트할 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> 에 데이터를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9dc-104">The control handles most of the logic that it must have to query against [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pass the data to the browser, retrieve it, and submit it to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> which then updates the database.</span></span> <span data-ttu-id="dc9dc-105">컨트롤을 태그에 구성하기만 하면 컨트롤이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 과 브라우저 사이의 모든 데이터 전송을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9dc-105">You just configure the control in the markup, and the control handles all the data transfer between [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] and the browser.</span></span> <span data-ttu-id="dc9dc-106">프레젠테이션 계층과의 상호 작용은 이 컨트롤이 처리하고 데이터 계층과의 통신은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 이 처리하기 때문에 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] 다계층 응용 프로그램에서 사용자는 사용자 지정 비즈니스 논리를 작성하는 데 집중해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9dc-106">Because the control handles the interactions with the presentation tier, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] handles the communication with the data tier, your main focus in [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] multitier applications is on writing your custom business logic.</span></span>  
  
 <span data-ttu-id="dc9dc-107">`LINQDataSource`에 대한 자세한 내용은 [NIB: LinqDataSource 웹 서버 컨트롤 개요](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc9dc-107">For more information about `LINQDataSource`, see [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc9dc-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc9dc-108">See Also</span></span>  
 [<span data-ttu-id="dc9dc-109">LINQ to SQL을 사용한 N 계층 및 원격 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="dc9dc-109">N-Tier and Remote Applications with LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
