---
title: "암호화 체계 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3e3c4a832f70fae7808bf71016cb9f6648332f01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-cryptographic-scheme"></a>암호화 체계 만들기
.NET Framework의 암호화 구성 요소를 결합하여 다양한 체계를 만들고 데이터를 암호화 및 암호 해독할 수 있습니다.  
  
 데이터 암호화 및 암호 해독을 위한 간단한 암호화 체계에서는 다음 단계를 지정할 수 있습니다.  
  
1.  각 당사자가 공개/개인 키 쌍을 생성합니다.  
  
2.  양쪽 당사자가 공개 키를 교환합니다.  
  
3.  예를 들어 각 당사자가 TripleDES 암호화를 위한 비밀 키를 생성하고 상대방의 공개 키를 사용하여 새로 만든 키를 암호화합니다.  
  
4.  각 당사자가 상대방에게 데이터를 보내고 상대방의 비밀 키와 자신의 비밀 키를 특정 순서로 결합하여 새 비밀 키를 만듭니다.  
  
5.  양쪽 당사자가 대칭 암호화를 사용하여 대화를 시작합니다.  
  
 암호화 체계를 만드는 과정은 간단한 작업이 아닙니다. 암호화 사용에 대한 자세한 내용은 http://msdn.microsoft.com/library에 있는 플랫폼 SDK 설명서의 암호화 항목을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
