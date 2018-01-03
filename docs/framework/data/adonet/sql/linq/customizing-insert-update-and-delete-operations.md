---
title: "삽입, 업데이트 및 삭제 작업을 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 99a87a3d0dfabb053ca05644e0b3e53361821b9b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="2d2f5-102">삽입, 업데이트 및 삭제 작업을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2d2f5-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="2d2f5-103">기본적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 동적 SQL을 생성하여 삽입, 읽기, 업데이트 및 삭제 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f5-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="2d2f5-104">그러나 실제로는 대개 비즈니스 요구에 맞게 응용 프로그램을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f5-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d2f5-105">[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 경우 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 통해 삽입, 업데이트 및 삭제 작업을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f5-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="2d2f5-106">이 항목의 단원에서는 사용자 응용 프로그램에서 삽입, 읽기, 업데이트, 삭제 작업을 사용자 지정하도록 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 제공하는 기술을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f5-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d2f5-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2d2f5-107">In This Section</span></span>  
 [<span data-ttu-id="2d2f5-108">작업 사용자 지정: 개요</span><span class="sxs-lookup"><span data-stu-id="2d2f5-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="2d2f5-109">삽입, 읽기, 업데이트 및 삭제 작업을 사용자 지정하도록 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 제공하는 다양한 기술을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f5-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="2d2f5-110">삽입, 업데이트 및 삭제 작업</span><span class="sxs-lookup"><span data-stu-id="2d2f5-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="2d2f5-111">데이터베이스 데이터 조작을 위한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기본 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f5-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="2d2f5-112">기본 동작 재정의에서 개발자의 책임</span><span class="sxs-lookup"><span data-stu-id="2d2f5-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="2d2f5-113">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 적용되지 않는 요구 사항 구현에 있어 개발자의 역할을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f5-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="2d2f5-114">Partial 메서드를 사용하여 비즈니스 논리 추가</span><span class="sxs-lookup"><span data-stu-id="2d2f5-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="2d2f5-115">부분 메서드(Partial Method)를 사용하여 자동 생성되는 메서드를 재정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f5-115">Describes how to use partial methods to override autogenerated methods.</span></span>
