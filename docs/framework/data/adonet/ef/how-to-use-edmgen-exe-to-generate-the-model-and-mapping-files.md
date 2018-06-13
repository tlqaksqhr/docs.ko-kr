---
title: '방법: EdmGen.exe를 사용하여 모델 생성 및 파일 매핑'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: d3e32e4883eea7ec304ceaf0bcdc939b9d12dde0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760949"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>방법: EdmGen.exe를 사용하여 모델 생성 및 파일 매핑
이 항목에서는 EDM 생성기(EdmGen.exe) 도구를 사용하여 School 데이터베이스를 기반으로 하는 다음 파일을 생성하는 방법을 보여 줍니다.  
  
-   개념적 모델(.csdl 파일)  
  
-   저장소 모델(.ssdl 파일)  
  
-   개념적 모델과 저장소 모델 간의 매핑(.msl 파일)  
  
-   Visual Basic 또는 C#의 개체 계층 코드  
  
-   뷰 파일  
  
 EdmGen.exe 도구에서는 /mode:FullGeneration을 사용하여 위에 나열된 파일을 생성합니다. EdmGen.exe 명령에 대 한 자세한 내용은 참조 [EDM 생성기 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)합니다.  
  
 EdmGen.exe를 사용 하 여 모델 및 매핑 파일을 생성 하는 경우 여전히 구성 해야 사용 하도록 Visual Studio 프로젝트는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다. 자세한 내용은 참조 [하는 방법: 수동으로 Entity Framework 프로젝트 구성](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)합니다.  
  
> [!NOTE]
>  EdmGen.exe에서 생성된 개념적 모델에는 데이터베이스의 모든 개체가 포함됩니다. 특정 개체만 포함된 개념적 모델을 생성하려면 엔터티 데이터 모델 마법사를 사용합니다. 자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>EdmGen.exe를 사용하여 Visual Basic 프로젝트용 School 모델을 생성하려면  
  
1.  School 데이터베이스를 만듭니다. 자세한 내용은 참조 [School 샘플 데이터베이스 만들기](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)합니다.  
  
2.  명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>EdmGen.exe를 사용하여 C# 프로젝트용 School 모델을 생성하려면  
  
1.  School 데이터베이스를 만듭니다. 자세한 내용은 참조 [School 샘플 데이터베이스 만들기](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)합니다.  
  
2.  명령 프롬프트에서 줄 바꿈 없이 다음 명령을 실행합니다.  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [모델링 및 매핑](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [방법: 수동으로 Entity Framework 프로젝트 구성](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [방법: 쿼리 성능을 개선 하는 뷰를 미리 생성](http://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [ADO.NET 엔터티 데이터 모델 도구](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [방법: EdmGen.exe를 사용하여 모델 유효성 검사 및 파일 매핑](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
