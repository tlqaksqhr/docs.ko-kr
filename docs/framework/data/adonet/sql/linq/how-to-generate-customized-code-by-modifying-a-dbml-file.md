---
title: '방법: DBML 파일을 수정하여 사용자 지정된 코드 생성'
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 806d0ebc0e9ce970e144d80dbbd4910f9d271e56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354574"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>방법: DBML 파일을 수정하여 사용자 지정된 코드 생성
데이터베이스 태그 언어 (.dbml) 메타 데이터 파일에서 Visual Basic 또는 C# 소스 코드를 생성할 수 있습니다. 이 방법을 사용하면 응용 프로그램 매핑 코드를 생성하기 전에 기본 .dbml 파일을 사용자 지정할 수 있습니다. 이는 고급 기능에 해당합니다.  
  
 이 프로세스의 단계는 다음과 같습니다.  
  
1.  .dbml 파일을 생성합니다.  
  
2.  편집기를 사용하여 .dbml 파일을 수정합니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml 파일용 스키마 정의 파일(.xsd)에 대해 .dbml 파일의 유효성을 검사해야 합니다. 자세한 내용은 참조 [LINQ to SQL에서에서 코드 생성](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)합니다.  
  
3.  Visual Basic 또는 C# 소스 코드를 생성 합니다.  
  
 다음 예제에서는 SQLMetal 명령줄 도구를 사용합니다. 자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드에서는 Northwind 샘플 데이터베이스에서 .dbml 파일을 생성합니다. 데이터베이스 메타데이터의 소스로 데이터베이스의 이름이나 .mdf 파일의 이름을 사용할 수 있습니다.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>예제  
 다음 코드는.dbml 파일에서 Visual Basic 또는 C# 소스 코드 파일을 생성합니다.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL에서 코드 생성](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [개체 모델 만들기](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
