---
title: "지역화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a>지역화
지역화는 응용 프로그램이 지 원하는 각 문화권에 대 한 지역화 된 버전에는 응용 프로그램의 리소스를 변환 하는 과정입니다. 완료 한 후에 지역화 단계를 진행 해야는 [지역화 가능성 검토](../../../docs/standard/globalization-localization/localizability-review.md) 전역화 된 응용 프로그램 지역화 될 준비가 되었는지 확인 하는 단계입니다.  
  
 지역화를 위해 준비 하는 응용 프로그램은 두 개의 개념적 블록, 모든 사용자 인터페이스 요소를 포함 하는 블록 및 실행 코드가 포함 된 블록으로 구분 됩니다. 사용자 인터페이스 블록 예: 문자열, 오류 메시지, 대화 상자, 메뉴, 중립 문화권에 대해 포함 된 개체 리소스를 지역화할 수 있는 사용자 인터페이스 요소에만 포함합니다. 코드 블록에는 모든 지원 되는 문화권에서 사용할 응용 프로그램 코드에만 포함 됩니다. 공용 언어 런타임 리소스와에서 응용 프로그램의 실행 코드를 구분 하는 위성 어셈블리 리소스 모델을 지원 합니다. 이 모델을 구현 하는 방법에 대 한 자세한 내용은 참조 [데스크톱 응용 프로그램의 리소스](../../../docs/framework/resources/index.md)합니다.  
  
 각 지역화 된 버전의 응용 프로그램에 대 한 지역화 된 사용자 인터페이스 블록의 대상 문화권에 대 한 적절 한 언어로 번역을 포함 하는 새 위성 어셈블리를 추가 합니다. 모든 문화권에 대 한 코드 블록 동일 하 게 유지 해야 합니다. 조합 된 코드 블록이 사용자 인터페이스 블록의 지역화 된 버전의 응용 프로그램의 지역화 된 버전을 생성합니다.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Windows Forms 리소스 편집기 (Winres.exe) 신속 하 게 대상 문화권에 대 한 Windows Forms를 지역화할 수 있도록 제공 합니다. 이 도구를 사용 하는 방법에 대 한 정보를 참조 하십시오. [Winres.exe (Windows Forms 리소스 편집기)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [전역화 및 지역화](../../../docs/standard/globalization-localization/index.md)  
 [지역화 가능성 검토](../../../docs/standard/globalization-localization/localizability-review.md)  
 [전역화](../../../docs/standard/globalization-localization/globalization.md)  
 [데스크톱 앱의 리소스](../../../docs/framework/resources/index.md)
