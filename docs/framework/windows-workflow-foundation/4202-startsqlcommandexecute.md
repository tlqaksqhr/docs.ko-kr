---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: 09e079864369115c773c58c451fc5e0a33a3ae9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510353"
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="02f05-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="02f05-102">4202 - StartSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="02f05-103">속성</span><span class="sxs-lookup"><span data-stu-id="02f05-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02f05-104">ID</span><span class="sxs-lookup"><span data-stu-id="02f05-104">ID</span></span>|<span data-ttu-id="02f05-105">4202</span><span class="sxs-lookup"><span data-stu-id="02f05-105">4202</span></span>|  
|<span data-ttu-id="02f05-106">키워드</span><span class="sxs-lookup"><span data-stu-id="02f05-106">Keywords</span></span>|<span data-ttu-id="02f05-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="02f05-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="02f05-108">수준</span><span class="sxs-lookup"><span data-stu-id="02f05-108">Level</span></span>|<span data-ttu-id="02f05-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="02f05-109">Verbose</span></span>|  
|<span data-ttu-id="02f05-110">채널</span><span class="sxs-lookup"><span data-stu-id="02f05-110">Channel</span></span>|<span data-ttu-id="02f05-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="02f05-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02f05-112">설명</span><span class="sxs-lookup"><span data-stu-id="02f05-112">Description</span></span>  
 <span data-ttu-id="02f05-113">SQL 명령이 실행되고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="02f05-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02f05-114">메시지</span><span class="sxs-lookup"><span data-stu-id="02f05-114">Message</span></span>  
 <span data-ttu-id="02f05-115">SQL 명령 실행 시작: %1</span><span class="sxs-lookup"><span data-stu-id="02f05-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="02f05-116">설명</span><span class="sxs-lookup"><span data-stu-id="02f05-116">Details</span></span>  
  
|<span data-ttu-id="02f05-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="02f05-117">Data Item Name</span></span>|<span data-ttu-id="02f05-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="02f05-118">Data Item Type</span></span>|<span data-ttu-id="02f05-119">설명</span><span class="sxs-lookup"><span data-stu-id="02f05-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="02f05-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="02f05-120">SqlCommand</span></span>|<span data-ttu-id="02f05-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="02f05-121">xs:string</span></span>|<span data-ttu-id="02f05-122">실행된 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="02f05-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="02f05-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="02f05-123">AppDomain</span></span>|<span data-ttu-id="02f05-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="02f05-124">xs:string</span></span>|<span data-ttu-id="02f05-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="02f05-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
