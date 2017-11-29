---
title: "클라이언트에서의 디버깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56f9ad05-ea1b-4ef6-85f2-890f7ed71567
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 38742bff446a09df5c549a87bd05177d764c63a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-on-the-client"></a><span data-ttu-id="8cf74-102">클라이언트에서의 디버깅</span><span class="sxs-lookup"><span data-stu-id="8cf74-102">Debugging on the Client</span></span>
<span data-ttu-id="8cf74-103">사용자가 클라이언트 응용 프로그램 작성을 쉽게 수행할 수 있도록 프로그램 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 추가할 수 있습니다는 [ \<serviceDebug >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) 서비스 동작을 서비스의 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="8cf74-103">To make it easier for users to write client applications for your [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service, you can add the [\<serviceDebug>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) service behavior to the configuration file of your service.</span></span> <span data-ttu-id="8cf74-104">이 동작을 사용하면 도움말 페이지를 게시하고, 클라이언트에 반환되는 SOAP 오류 정보에 관리되는 예외 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf74-104">This behavior can be used to publish help pages, and return managed exception information in the details of SOAP faults returned to the client.</span></span>
