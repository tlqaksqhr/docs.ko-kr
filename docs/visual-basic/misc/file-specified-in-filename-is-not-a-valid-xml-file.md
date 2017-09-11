---
title: "파일 이름에 지정 된 파일은 유효한 XML 파일이 아닙니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8b46b9d896f0dce401992e8a20e040b85091ba5d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="152c1-102">FileName에 지정된 파일은 유효한 XML 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="152c1-103">제공한 파일 이름이 유효한 XML 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="152c1-104">XML 문서의 허용된 구조와 내용을 지정하려면 DTD(문서 종류 정의), Microsoft XDR(XML-Data Reduced) 스키마 또는 XSD(XML 스키마 정의 언어) 스키마를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="152c1-105">XSD 스키마는 XML 문법에 지정 하는 기본 방법은 [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="152c1-106">일부 이전 버전의 Visual Studio에서 **XML 디자이너** 는 입력된 데이터 집합 및 XML 스키마용 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="152c1-107">**XML 디자이너** 는 XML 스키마 파일을 만들고 편집하는 데 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="152c1-108">그러나 [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], 만들기 및 편집 형식화 된 데이터 집합에 대 한 디자이너는는 **데이터 집합 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-108">However, in [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="152c1-109">자세한 내용은 참조 [만들기 및 형식화 된 데이터 집합 편집](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets)합니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="152c1-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="152c1-110">To correct this error</span></span>  
  
-   <span data-ttu-id="152c1-111">올바른 파일 이름을 제공했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-111">Check that you are supplying the correct file name.</span></span>  
  
-   <span data-ttu-id="152c1-112">확인하려는 XML 파일을 **XML 디자이너**로 로드하여 지정된 파일에 유효한 XML 파일이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="152c1-113">**XML** 메뉴에서 **XML 유효성 검사**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="152c1-114">**작업 목록**에 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-114">Errors are displayed in the **Task List**.</span></span>  
  
-   <span data-ttu-id="152c1-115">XML 파일에 연결된 XML 스키마가 있는 경우 요소가 정의된 구조에 표시되고 개별 요소의 콘텐츠가 스키마에서 지정된 선언된 데이터 형식에 맞는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="152c1-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="152c1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="152c1-116">See Also</span></span>  
 <span data-ttu-id="152c1-117"><xref:System.Xml></xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="152c1-117"><xref:System.Xml></span></span>   
<span data-ttu-id="152c1-118"> [방법: 파일 경로의 구문 분석](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span><span class="sxs-lookup"><span data-stu-id="152c1-118"> [How to: Parse File Paths](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span></span>
