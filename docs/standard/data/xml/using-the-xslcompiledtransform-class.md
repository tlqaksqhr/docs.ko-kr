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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a00ae5a2f54aee3d6ac16d0870f9171fe42ca289
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2018
---
# <a name="using-the-xslcompiledtransform-class"></a>XslCompiledTransform 클래스 사용
<xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 Microsoft .NET Framework XSLT 프로세서입니다. 이 클래스를 사용하여 스타일시트를 컴파일하고 XSLT 변환을 실행할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Xml.Xsl.XslCompiledTransform> 클래스의 전체적인 성능이 <xref:System.Xml.Xsl.XslTransform> 클래스보다 좋지만 <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 클래스의 <xref:System.Xml.Xsl.XslCompiledTransform> 메서드는 변환에 대해 처음 호출될 때 <xref:System.Xml.Xsl.XslTransform.Load%2A> 클래스의 <xref:System.Xml.Xsl.XslTransform> 메서드보다 느리게 수행될 수 있습니다. 이는 XSLT 파일이 로드되기 전에 컴파일되어야 하기 때문입니다. 자세한 내용은 [XslCompiledTransform Slower than XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/)(XslCompiledTransform이 XslTransform보다 느린가?)라는 블로그 게시물을 참조하세요.  
  
## <a name="in-this-section"></a>섹션 내용  
 [XslCompiledTransform 클래스에 대한 입력](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 사용할 수 있는 XSLT 입력 옵션에 대해 설명합니다.  
  
 [XslCompiledTransform 클래스의 출력 옵션](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 사용할 수 있는 XSLT 출력 옵션에 대해 설명합니다.  
  
 [XSLT 처리 중 외부 리소스 확인](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 <xref:System.Xml.XmlResolver> 클래스를 사용하여 외부 리소스를 확인하는 방법을 설명합니다.  
  
 [XSLT 스타일시트 확장](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 XSLT 확장을 지원하는 방법을 설명합니다.  
  
|||  
|-|-|  
|[복구할 수 있는 XSLT 오류](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|W3C(World Wide Web 컨소시엄) XSLT 1.0 권장 사항에서 허용하는 임의 동작 및 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 임의 동작을 처리하는 방법을 보여줍니다.|  
|[방법: 노드 조각 변형](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|노드 조각을 변형하는 방법을 설명합니다.|  
  
## <a name="related-sections"></a>관련 단원  
 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <xref:System.Xml.Xsl.XslTransform> 클래스에서 코드를 마이그레이션하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Xsl.XsltSettings>  
 <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
