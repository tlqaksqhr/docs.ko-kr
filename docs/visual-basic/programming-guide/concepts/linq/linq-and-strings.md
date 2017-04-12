---
title: "LINQ 및 문자열 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a79d1427331070da9c545fdd3175115fe187e879
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-strings-visual-basic"></a>LINQ 및 문자열 (Visual Basic)
LINQ는 문자열 및 문자열 컬렉션을 쿼리하고 변환에 사용할 수 있습니다. 반 구조화 된 데이터를 텍스트 파일에에서 특히 유용 합니다. 기존의 문자열 함수 및 정규식 LINQ 쿼리를 결합할 수 있습니다. 예를 들어, 사용할 수는 <xref:System.String.Split%2A>또는 <xref:System.Text.RegularExpressions.Regex.Split%2A>있습니다 후 쿼리 또는 수정할 수 있는 LINQ를 사용 하 여 문자열의 배열을 만드는 메서드를.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A> 사용할 수는 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>에서 메서드는 `where` LINQ 쿼리 절.</xref:System.Text.RegularExpressions.Regex.IsMatch%2A> LINQ를 사용 하 여를 쿼리하거나 수정 하는 <xref:System.Text.RegularExpressions.MatchCollection>정규식에 의해 반환 된 결과입니다.</xref:System.Text.RegularExpressions.MatchCollection>  
  
 또한 반 구조화 된 텍스트 데이터를 XML로 변환 하이 섹션에 설명 된 기법을 사용할 수 있습니다. 자세한 내용은 참조 [하는 방법: CSV 파일에서 XML 생성](how-to-generate-xml-from-csv-files.md)합니다.  
  
 이 섹션의 예에서는 두 가지 범주로 구분 됩니다.  
  
## <a name="querying-a-block-of-text"></a>텍스트 블록을 쿼리합니다.  
 쿼리, 분석 및 사용 하 여 쿼리 가능한 작은 문자열 배열로 분할 하 여 텍스트 블록을 수정할 수는 <xref:System.String.Split%2A>메서드 또는 <xref:System.Text.RegularExpressions.Regex.Split%2A>메서드.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A> 단어, 문장, 단락, 페이지 또는 기타 기준으로 소스 텍스트를 분할 하 고 쿼리에 요구 하는 경우 추가 분할을 수행할 수 있습니다.  
  
 [방법: 문자열 (LINQ) (Visual Basic)에서 단어 수 계산](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 간단 하 게 쿼리 텍스트에 대 한 LINQ를 사용 하는 방법을 보여 줍니다.  
  
 [방법: 지정된 된 단어 (LINQ) (Visual Basic) 집합이 들어 있는 문장 쿼리](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 임의의 경계에서 텍스트 파일을 분할 하는 방법과 각 부분에 대해 쿼리를 수행 하는 방법을 보여 줍니다.  
  
 [방법: 문자열 (Visual Basic) (LINQ)의 문자에 대 한 쿼리](how-to-query-for-characters-in-a-string-linq.md)  
 문자열이 쿼리 가능한 형식 인지를 보여 줍니다.  
  
 [방법: LINQ 쿼리와 정규식 (Visual Basic)를 결합 합니다.](how-to-combine-linq-queries-with-regular-expressions.md)  
 필터링 된 쿼리 결과 대해 일치 하는 복잡 한 패턴에 대 한 LINQ 쿼리에서 정규식을 사용 하는 방법을 보여 줍니다.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>텍스트 형식으로 반 구조화 된 데이터 쿼리  
 다양 한 유형의 텍스트 파일 일련의 탭 또는 쉼표로 구분 된 파일 또는 고정 길이 줄과 같은 유사한 형식을 함께 줄으로 이루어져 있습니다. 이러한 텍스트 파일을 메모리로 읽어 들인 후 쿼리 및/또는 줄을 수정 하려면 LINQ를 사용할 수 있습니다. LINQ 쿼리는 또한 여러 원본의 데이터를 결합 하 여 작업을 간소화 합니다.  
  
 [방법: 두 목록 (Visual Basic) (LINQ) 간의 차집합 구하기](how-to-find-the-set-difference-between-two-lists-linq.md)  
 다른 리소스는 제외 목록에 있는 모든 문자열을 찾는 방법을 보여 줍니다.  
  
 [방법: 데이터 정렬 또는 필터링 텍스트에서 단어 또는 필드 (Visual Basic) (LINQ)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 단어 또는 필드에 따라 텍스트 줄을 정렬 하는 방법을 보여 줍니다.  
  
 [방법: 구분된 된 파일 (Visual Basic) (LINQ)의 필드 다시 정렬](how-to-reorder-the-fields-of-a-delimited-file.md)  
 .Csv 파일의 줄의 필드 순서를 변경 하는 방법을 보여 줍니다.  
  
 [방법: 문자열 컬렉션 (Visual Basic) (LINQ) 결합 및 비교](how-to-combine-and-compare-string-collections-linq.md)  
 다양 한 방법으로 문자열 목록을 조합 하는 방법을 보여 줍니다.  
  
 [방법: 개체 컬렉션 (Visual Basic) (LINQ) 여러 소스에서 채우기](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 데이터 원본으로 여러 텍스트 파일을 사용 하 여 개체 컬렉션을 만드는 방법을 보여 줍니다.  
  
 [방법: 서로 다른 파일 (Visual Basic) (LINQ)의 콘텐츠 조인](how-to-join-content-from-dissimilar-files-linq.md)  
 일치 하는 키를 사용 하 여 두 목록에서 문자열을 단일 문자열로 결합 하는 방법을 보여 줍니다.  
  
 [방법: 그룹 (LINQ) (Visual Basic)를 사용 하 여 파일을 여러 파일로 분할](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 단일 파일을 데이터 원본으로 사용 하 여 새 파일을 만드는 방법을 보여 줍니다.  
  
 [방법: CSV 텍스트 파일 (Visual Basic) (LINQ)의 열 값 계산](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 .Csv 파일에서 텍스트 데이터에 대해 수학적 계산을 수행 하는 방법을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [언어 통합 쿼리 (LINQ) (Visual Basic)](index.md)   
 [방법: CSV 파일에서 XML 생성](how-to-generate-xml-from-csv-files.md)

