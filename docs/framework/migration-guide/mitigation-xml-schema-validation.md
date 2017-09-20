---
title: "완화: XML 스키마 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 786e2d0d70aaead6d464d262ca43dade8db64a52
ms.contentlocale: ko-kr
ms.lasthandoff: 09/19/2017

---
# <a name="mitigation-xml-schema-validation"></a>완화: XML 스키마 유효성 검사
[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 복합 키를 사용하고 한 개의 키가 비어 있는 경우 XSD 스키마 유효성 검사가 고유한 제약 조건 위반을 검색합니다.  
  
## <a name="impact"></a>영향  
 이 변경에 따른 영향이 최소화되어야 합니다. 빈 키가 포함된 복합 키를 사용함으로써 `xsd:unique`가 위반된 경우 스키마 사양에 따라 스키마 유효성 검사 오류가 예상됩니다.  
  
## <a name="mitigation"></a>완화  
 복합 키에 한 개의 빈 키가 있는 경우 스키마 유효성 검사 오류 검색 여부는 구성 가능한 기능입니다.  
  
-   [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]을 대상으로 하는 앱부터 스키마 유효성 검사 오류 검색은 기본적으로 사용하도록 설정되어 있습니다. 그러나 스키마 유효성 검사 오류가 검색되지 않도록 이 기능을 옵트아웃(opt out)할 수 있습니다.  
  
-   [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 실행되지만 [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] 및 이전 버전을 대상으로 하는 앱에서는 스키마 유효성 검사 오류가 기본적으로 검색되지 않습니다. 그러나 스키마 유효성 검사 오류가 검색되도록 이 기능을 옵트인(opt in)할 수 있습니다.  
  
 이 동작은 <xref:System.AppContext> 클래스를 사용하여 `System.Xml.IgnoreEmptyKeySequences` 스위치의 값을 정의하도록 구성할 수 있습니다. 스위치의 기본값은 `false`(빈 키 시퀀스가 무시되지 않음)이기 때문에 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]을 대상으로 하는 앱은 다음 코드를 사용하여 스위치의 값을 `true`로 설정하면 해당 동작을 옵트아웃(opt out)할 수 있습니다.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] 및 이전 버전을 대상으로 하는 앱의 경우 스위치의 기본값이`true`(빈 키 시퀀스가 무시됨)이기 때문에 다음 코드를 사용하여 스위치의 값을 `false`로 설정하면 빈 키가 포함된 복합 키가 스키마 유효성 검사 오류를 생성하도록 할 수 있습니다.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

