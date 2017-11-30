---
title: "XslCompiledTransform 클래스 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a5c71a7796790343bf39de5bbfd03997c25d5f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-xslcompiledtransform-class"></a>XslCompiledTransform 클래스 사용
<xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 Microsoft .NET Framework XSLT 프로세서입니다. 이 클래스를 사용하여 스타일시트를 컴파일하고 XSLT 변환을 실행할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Xml.Xsl.XslCompiledTransform> 클래스의 전체적인 성능이 <xref:System.Xml.Xsl.XslTransform> 클래스보다 좋지만 <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 클래스의 <xref:System.Xml.Xsl.XslCompiledTransform> 메서드는 변환에 대해 처음 호출될 때 <xref:System.Xml.Xsl.XslTransform.Load%2A> 클래스의 <xref:System.Xml.Xsl.XslTransform> 메서드보다 느리게 수행될 수 있습니다. 이는 XSLT 파일이 로드되기 전에 컴파일되어야 하기 때문입니다. 자세한 내용은 다음 블로그 게시물을 참조 하십시오.: [XslCompiledTransform이 XslTransform 보다 느린?](http://go.microsoft.com/fwlink/?LinkId=130590)  
  
## <a name="in-this-section"></a>단원 내용  
 [XslCompiledTransform 클래스에 대 한 입력](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 사용할 수 있는 XSLT 입력 옵션에 대해 설명합니다.  
  
 [XslCompiledTransform 클래스에 대 한 출력 옵션](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 사용할 수 있는 XSLT 출력 옵션에 대해 설명합니다.  
  
 [XSLT 처리 중 외부 리소스 확인](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 <xref:System.Xml.XmlResolver> 클래스를 사용하여 외부 리소스를 확인하는 방법을 설명합니다.  
  
 [XSLT 스타일 시트 확장](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 XSLT 확장을 지원하는 방법을 설명합니다.  
  
|||  
|-|-|  
|[복구할 수 있는 XSLT 오류](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|W3C(World Wide Web 컨소시엄) XSLT 1.0 권장 사항에서 허용하는 임의 동작 및 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 임의 동작을 처리하는 방법을 보여 줍니다.|  
|[방법: 노드 조각을 변환](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|노드 조각을 변형하는 방법을 설명합니다.|  
  
## <a name="related-sections"></a>관련 단원  
 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <xref:System.Xml.Xsl.XslTransform> 클래스에서 코드를 마이그레이션하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Xsl.XsltSettings>  
 <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
