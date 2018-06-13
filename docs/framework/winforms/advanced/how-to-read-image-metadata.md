---
title: '방법: 이미지 메타데이터 읽기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 92ce4eb8d51fbd25f9a129a629dc47bfb9941f34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526580"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="ea835-102">방법: 이미지 메타데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="ea835-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="ea835-103">일부 이미지 파일 이미지의 기능을 확인 읽을 수 있는 메타 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="ea835-104">예를 들어 디지털 사진 제조업체와 이미지를 캡처하는 데 사용 하는 카메라 모델을 확인 하려면 읽을 수 있는 메타 데이터를 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="ea835-105">와 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 기존 메타 데이터를 읽을 수 있습니다 및 이미지 파일에 새 메타 데이터를 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-105">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="ea835-106"> 메타 데이터는 개별 부분을 저장 한 <xref:System.Drawing.Imaging.PropertyItem> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-106"> stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="ea835-107">읽을 수는 <xref:System.Drawing.Image.PropertyItems%2A> 속성은 <xref:System.Drawing.Image> 파일에서 모든 메타 데이터를 검색할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="ea835-108"><xref:System.Drawing.Image.PropertyItems%2A> 속성의 배열을 반환 <xref:System.Drawing.Imaging.PropertyItem> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="ea835-109">A <xref:System.Drawing.Imaging.PropertyItem> 개체에는 다음 네 가지 속성이: `Id`, `Value`, `Len`, 및 `Type`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="ea835-110">ID</span><span class="sxs-lookup"><span data-stu-id="ea835-110">Id</span></span>  
 <span data-ttu-id="ea835-111">메타 데이터 항목을 식별 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="ea835-112">에 할당할 수 있는 일부 값 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="ea835-113">16 진수 값</span><span class="sxs-lookup"><span data-stu-id="ea835-113">Hexadecimal value</span></span>|<span data-ttu-id="ea835-114">설명</span><span class="sxs-lookup"><span data-stu-id="ea835-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="ea835-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="ea835-115">0x0320</span></span><br /><br /> <span data-ttu-id="ea835-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="ea835-116">0x010F</span></span><br /><br /> <span data-ttu-id="ea835-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="ea835-117">0x0110</span></span><br /><br /> <span data-ttu-id="ea835-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="ea835-118">0x9003</span></span><br /><br /> <span data-ttu-id="ea835-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="ea835-119">0x829A</span></span><br /><br /> <span data-ttu-id="ea835-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="ea835-120">0x5090</span></span><br /><br /> <span data-ttu-id="ea835-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="ea835-121">0x5091</span></span>|<span data-ttu-id="ea835-122">이미지 제목</span><span class="sxs-lookup"><span data-stu-id="ea835-122">Image title</span></span><br /><br /> <span data-ttu-id="ea835-123">장치 제조업체</span><span class="sxs-lookup"><span data-stu-id="ea835-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="ea835-124">장치 모델</span><span class="sxs-lookup"><span data-stu-id="ea835-124">Equipment model</span></span><br /><br /> <span data-ttu-id="ea835-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="ea835-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="ea835-126">Exif 노출 시간</span><span class="sxs-lookup"><span data-stu-id="ea835-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="ea835-127">광도 테이블</span><span class="sxs-lookup"><span data-stu-id="ea835-127">Luminance table</span></span><br /><br /> <span data-ttu-id="ea835-128">색차 테이블</span><span class="sxs-lookup"><span data-stu-id="ea835-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="ea835-129">값</span><span class="sxs-lookup"><span data-stu-id="ea835-129">Value</span></span>  
 <span data-ttu-id="ea835-130">배열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-130">An array of values.</span></span> <span data-ttu-id="ea835-131">값의 형식은 따라 사용자가 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="ea835-132">Len</span><span class="sxs-lookup"><span data-stu-id="ea835-132">Len</span></span>  
 <span data-ttu-id="ea835-133">(바이트)의 길이 값의 배열에서 가리키는 <xref:System.Drawing.Imaging.PropertyItem.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="ea835-134">형식</span><span class="sxs-lookup"><span data-stu-id="ea835-134">Type</span></span>  
 <span data-ttu-id="ea835-135">배열에 있는 값의 데이터 형식에서 가리키는 `Value` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="ea835-136">나타내는 형식이 `Type` 속성 값은 다음 표와</span><span class="sxs-lookup"><span data-stu-id="ea835-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="ea835-137">숫자 값</span><span class="sxs-lookup"><span data-stu-id="ea835-137">Numeric value</span></span>|<span data-ttu-id="ea835-138">설명</span><span class="sxs-lookup"><span data-stu-id="ea835-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="ea835-139">1</span><span class="sxs-lookup"><span data-stu-id="ea835-139">1</span></span>|<span data-ttu-id="ea835-140">`Byte`입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-140">A `Byte`</span></span>|  
|<span data-ttu-id="ea835-141">2</span><span class="sxs-lookup"><span data-stu-id="ea835-141">2</span></span>|<span data-ttu-id="ea835-142">배열 `Byte` ASCII로 인코딩된 개체</span><span class="sxs-lookup"><span data-stu-id="ea835-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="ea835-143">3</span><span class="sxs-lookup"><span data-stu-id="ea835-143">3</span></span>|<span data-ttu-id="ea835-144">16 비트 정수</span><span class="sxs-lookup"><span data-stu-id="ea835-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="ea835-145">4</span><span class="sxs-lookup"><span data-stu-id="ea835-145">4</span></span>|<span data-ttu-id="ea835-146">32 비트 정수</span><span class="sxs-lookup"><span data-stu-id="ea835-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="ea835-147">5</span><span class="sxs-lookup"><span data-stu-id="ea835-147">5</span></span>|<span data-ttu-id="ea835-148">두 배열 `Byte` 분수를 나타내는 개체를</span><span class="sxs-lookup"><span data-stu-id="ea835-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="ea835-149">6</span><span class="sxs-lookup"><span data-stu-id="ea835-149">6</span></span>|<span data-ttu-id="ea835-150">사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="ea835-150">Not used</span></span>|  
|<span data-ttu-id="ea835-151">7</span><span class="sxs-lookup"><span data-stu-id="ea835-151">7</span></span>|<span data-ttu-id="ea835-152">Undefined</span><span class="sxs-lookup"><span data-stu-id="ea835-152">Undefined</span></span>|  
|<span data-ttu-id="ea835-153">8</span><span class="sxs-lookup"><span data-stu-id="ea835-153">8</span></span>|<span data-ttu-id="ea835-154">사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="ea835-154">Not used</span></span>|  
|<span data-ttu-id="ea835-155">10</span><span class="sxs-lookup"><span data-stu-id="ea835-155">9</span></span>|`SLong`|  
|<span data-ttu-id="ea835-156">10</span><span class="sxs-lookup"><span data-stu-id="ea835-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="ea835-157">예제</span><span class="sxs-lookup"><span data-stu-id="ea835-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ea835-158">설명</span><span class="sxs-lookup"><span data-stu-id="ea835-158">Description</span></span>  
 <span data-ttu-id="ea835-159">다음 코드 예제에서는 파일의 일곱 가지 메타 데이터 표시를 읽고 `FakePhoto.jpg`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="ea835-160">목록에서 두 번째 (인덱스 1) 속성 항목에 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 는 0x010F (주문자) 및 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII로 인코딩된 바이트 배열)입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="ea835-161">코드 예제에서는 해당 속성 항목의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="ea835-162">코드에는 다음과 유사한 출력이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-162">The code produces output similar to the following:</span></span>  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a><span data-ttu-id="ea835-163">코드</span><span class="sxs-lookup"><span data-stu-id="ea835-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ea835-164">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ea835-164">Compiling the Code</span></span>  
 <span data-ttu-id="ea835-165">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="ea835-166">폼의 처리 <xref:System.Windows.Forms.Control.Paint> 이벤트 하 paint 이벤트 처리기에이 코드를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="ea835-167">바꾸어야 `FakePhoto.jpg` 이미지 이름 및 경로 시스템 및 가져오기에 사용할 수는 `System.Drawing.Imaging` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ea835-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea835-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea835-168">See Also</span></span>  
 [<span data-ttu-id="ea835-169">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="ea835-169">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="ea835-170">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="ea835-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
