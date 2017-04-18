---
title: "ClaimSet에서 클레임 찾기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "클레임 [WCF]"
  - "클레임 [WCF], claimset에서 찾기"
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ClaimSet에서 클레임 찾기
클레임 기준 권한 부여를 사용하는 경우 <xref:System.IdentityModel.Claims.ClaimSet>의 콘텐츠에서 특정 형식의 클레임을 확인하는 작업이 일반적으로 수행됩니다.<xref:System.IdentityModel.Claims.ClaimSet>에 특정 클레임이 있는지 확인하려면 <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> 메서드를 사용합니다.이 메서드가 <xref:System.IdentityModel.Claims.ClaimSet>을 직접 반복하는 것보다 더 성능이 좋습니다.다음은 이렇게 사용하는 경우의 예입니다.`claimType` 및 `claimRight` 매개 변수는 `null`일 수 있습니다.이 경우 매개 변수에서는 모든 클레임 형식과 클레임 권한을 일치시킵니다.  
  
## 예제  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## 참고 항목  
 [ID 모델을 사용하여 클레임 및 권한 부여 관리](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)