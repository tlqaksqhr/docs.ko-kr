---
title: "자습서: WordprocessingML 문서에서 내용 조작(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bc9815f8-13d2-4f50-a4d1-b1c0d50d37b3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e36db410781765c6861f60942782bbd6259d5de8
ms.lasthandoff: 03/13/2017


---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-c"></a>자습서: WordprocessingML 문서에서 내용 조작(C#)
이 자습서에서는 함수 변환 방법과 LINQ to XML을 적용하여 XML 문서를 조작하는 방법을 보여 줍니다. C# 예제에서는 Microsoft Word에서 저장한 Office Open XML WordprocessingML 문서의 정보를 쿼리하고 조작합니다.  
  
 자세한 내용은 [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) 웹 사이트를 참조하세요.  
  
## <a name="in-this-section"></a>단원 내용  
  
|항목|설명|  
|-----------|-----------------|  
|[WordprocessingML 문서의 모양(C#)](../../../../csharp/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|WordprocessingML 문서에 대해 간략히 설명합니다.|  
|[원본 Office Open XML 문서 만들기(C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|이 자습서의 쿼리에 대한 소스 문서를 만드는 단계별 지침을 제공합니다.|  
|[기본 단락 스타일 찾기(C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|문서에 대한 기본 스타일의 이름을 찾는 쿼리를 보여 줍니다.|  
|[단락 및 해당 스타일 검색(C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|문서의 단락 컬렉션을 검색하는 쿼리를 보여 줍니다.|  
|[단락의 텍스트 검색(C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|이전 쿼리를 확대하여 각 단락의 텍스트를 검색합니다.|  
|[확장 메서드를 사용하여 리팩터링(C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|확장명 메서드를 통해 리팩터링하여 코드를 단순화합니다.|  
|[순수 함수를 사용하여 리팩터링(C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|순수 함수를 통해 리팩터링하여 코드를 더 단순화합니다.|  
|[다른 모양으로 XML 프로젝션(C#)](../../../../csharp/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|원래 문서와 다른 모양으로 XML을 프로젝션하여 XML 변환을 완료합니다.|  
|[Word 문서에서 텍스트 찾기(C#)](../../../../csharp/programming-guide/concepts/linq/finding-text-in-word-documents.md)|이전 쿼리를 사용하여 문서에서 지정된 텍스트 문자열을 찾습니다.|  
|[Office Open XML WordprocessingML 문서 정보(C#)](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|Office Open XML WordprocessingML 문서에 대해 설명합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [XML의 순수 함수 변환(C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)   
 [순수 함수 변환 소개(C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
