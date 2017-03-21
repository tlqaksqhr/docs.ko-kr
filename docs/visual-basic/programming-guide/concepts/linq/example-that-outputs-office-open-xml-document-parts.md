---
title: "Office Open XML 문서 요소 (Visual Basic)를 출력 하는 예제 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: a951925b-c985-48ed-b215-2a68b58f1ae5
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 72e8cd6126cd049cafff6e18e1ef609f600cf7c9
ms.lasthandoff: 03/13/2017


---
# <a name="example-that-outputs-office-open-xml-document-parts-visual-basic"></a>Office Open XML 문서 요소 (Visual Basic)를 출력 하는 예제
이 항목에서는 Office Open XML 문서를 열고 문서 안의 부분에 액세스하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 Office Open XML 문서를 열고 문서 부분과 스타일 부분을 콘솔에 출력합니다.  
  
 이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고 형식을 사용는 <xref:System.IO.Packaging?displayProperty=fullName>네임 스페이스.</xref:System.IO.Packaging?displayProperty=fullName>  
  
```vb  
Const fileName As String = "SampleDoc.docx"  
  
Const documentRelationshipType As String = _  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
Const stylesRelationshipType As String = _  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
Const wordmlNamespace As String = _  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
Dim w As XNamespace = wordmlNamespace  
  
Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
    Dim docPackageRelationship As PackageRelationship = _  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
    If docPackageRelationship IsNot Nothing Then  
        Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
          docPackageRelationship.TargetUri)  
        Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
        ' Load the document XML in the part into an XDocument instance.  
        Dim xdoc As XDocument = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
        Console.WriteLine("TargetUri:{0}", docPackageRelationship.TargetUri)  
        Console.WriteLine("==================================================================")  
        Console.WriteLine(xdoc.Root)  
        Console.WriteLine()  
  
        ' Find the styles part. There will only be one.  
        Dim styleRelation As PackageRelationship = _  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
        If styleRelation IsNot Nothing Then  
            Dim styleUri As Uri = _  
              PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
            Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
            ' Load the style XML in the part into an XDocument instance.  
            Dim styleDoc As XDocument = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
  
            Console.WriteLine("TargetUri:{0}", styleRelation.TargetUri)  
            Console.WriteLine("==================================================================")  
            Console.WriteLine(styleDoc.Root)  
            Console.WriteLine()  
        End If  
    End If  
End Using  
```  
  
## <a name="see-also"></a>참고 항목  
 [세부 정보는 Office Open XML WordprocessingML 문서 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)
