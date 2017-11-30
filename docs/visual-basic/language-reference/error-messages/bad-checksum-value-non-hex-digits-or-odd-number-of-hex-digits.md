---
title: "체크섬 값이 잘못되었습니다. 16진수가 아니거나 16진수 값이 홀수입니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords: BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1158742c8eaa51bcbb5607795f16ae6c2b570db4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a>체크섬 값이 잘못되었습니다. 16진수가 아니거나 16진수 값이 홀수입니다.
체크섬 값의 16진수가 잘못되었거나 자릿수가 홀수입니다.  
  
 ASP.NET은 Visual Basic 소스 파일(확장명 .vb)을 생성할 때 체크섬을 계산하여 `#externalchecksum`으로 식별되는 숨겨진 소스 파일에 저장합니다. .vb 파일을 생성하는 사용자도 이 작업을 수행할 수 있지만 해당 프로세스는 내부용으로 유지하는 것이 가장 좋습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC42033  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  ASP.NET에서 Visual Basic 소스 파일을 생성하는 경우 프로젝트 빌드를 다시 시작합니다.  
  
2.  빌드를 다시 시작한 후에도 이 경고가 계속 발생하면 ASP.NET을 다시 설치하고 빌드를 다시 시도합니다.  
  
3.  그래도 경고가 계속 발생하거나 ASP.NET을 사용하고 있지 않으면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
## <a name="see-also"></a>참고 항목  
 [ASP.NET 개요](https://msdn.microsoft.com/library/4w3ex9c2.aspx)  
 [의견 보내기](/visualstudio/ide/talk-to-us)
