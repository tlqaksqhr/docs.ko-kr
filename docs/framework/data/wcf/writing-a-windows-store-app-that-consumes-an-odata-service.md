---
title: "OData 서비스를 사용하는 Windows 스토어 앱 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
ms.assetid: 9917a0e9-ec93-49e5-a366-fd39b892eb8b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a2eb79e8bf8a5c683c9d48a0a69e4d7f5d270eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="writing-a-windows-store-app-that-consumes-an-odata-service"></a>OData 서비스를 사용하는 Windows 스토어 앱 작성
Windows 8에는 응용 프로그램의 새로운 종류: Windows 스토어 응용 프로그램입니다. 완전히 새로운 모양과 느낌의 Windows 스토어 앱은 다양한 장치에서 실행되며 Windows 스토어에서 구할 수 있습니다. 이 항목에서는 OData 서비스, 특히 NetFlix Catalog OData 서비스를 사용하는 Windows 스토어 앱을 작성하는 방법을 설명합니다. Windows 스토어 앱에 대 한 자세한 내용은 읽으십시오 [Windows 스토어 앱 시작](http://msdn.microsoft.com/library/windows/apps/br211386.aspx)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
  
1.  [Microsoft Windows 8](http://go.microsoft.com/fwlink/p/?LinkId=266654)  
  
2.  [Microsoft Visual Studio 2012](http://go.microsoft.com/fwlink/p/?LinkId=266655)  
  
3.  [WCF 데이터 서비스](http://msdn.microsoft.com/data/bb931106)  
  
#### <a name="creating-the-default-windows-store-grid-application"></a>기본 Windows 스토어 표 형태 응용 프로그램 만들기  
  
1.  C# 및 XAML을 사용하여 새 Windows 스토어 표 형태 응용 프로그램을 만들고 이름을 OData.WindowsStore.NetflixDemo로 지정합니다.  
  
     ![새 프로젝트 대화 상자](../../../../docs/framework/data/wcf/media/win8clientcreatenewproject.png "Win8ClientCreateNewProject")  
  
2.  Package.appxmanifest를 열고 표시 이름 텍스트 상자에 이름을 입력합니다. 이 이름은 Windows 8 검색 기능에 사용되는 응용 프로그램 이름입니다.  
  
     ![응용 프로그램 매니페스트 파일](../../../../docs/framework/data/wcf/media/appxmanifest.png "appxmanifest가")  
  
3.  에 친숙 한 이름을 입력는 \<응용 프로그램 이름 > App.xaml 파일의 요소입니다. 이렇게 하면 응용 프로그램이 시작될 때 표시되는 응용 프로그램 이름이 설정됩니다.  
  
     ![App.xaml 파일](../../../../docs/framework/data/wcf/media/appxaml.png "appxaml")  
  
4.  응용 프로그램을 빌드하고 시작합니다. 먼저 응용 프로그램 시작 화면이 표시됩니다. 아래 스크린샷은 기본 시작 화면입니다. 사용되는 이미지는 프로젝트의 Assets 폴더에 저장됩니다.  
  
     ![기본 앱 시작 화면](../../../../docs/framework/data/wcf/media/defualtappsplash.png "defualtAppSplash")  
  
     그런 다음 응용 프로그램이 표시됩니다.  
  
     ![기본 응용 프로그램](../../../../docs/framework/data/wcf/media/defaultapplication.png "DefaultApplication")  
  
     기본 응용 프로그램은 SampleDataSource.cs: SampleDataGroup 및 SampleDataItem에 클래스 집합을 정의합니다. SampleDataSource.cs: SampleDataGroup 및 SampleDataItem은 모두 SampleDataCommon에서 파생되며 SampleDataCommon은 BindableBase에서 파생됩니다. SampleDataGroup 및 SampleDataItem은 기본 GridView에 바인딩됩니다. SampleDataSource.cs는 NetflixDemo 프로젝트 내의 DataModel 폴더에 있습니다. 응용 프로그램에 그룹화된 컬렉션이 표시됩니다. 각 그룹에는 각각 SampleDataGroup 및 SampleDataItem으로 나타나는 임의 개수의 항목이 있습니다. 위의 스크린샷을 보면 Group Title 1이라는 그룹이 있고 이 그룹의 모든 항목은 함께 표시됩니다.  
  
     응용 프로그램의 기본 페이지는 GroupedItemsPage.xaml입니다. 이 페이지에는 SampleDataSource.cs 클래스에서 만든 샘플 데이터가 표시되는 GridView가 있습니다. GroupedItemsPage는 rootFrame.Navigate가 호출될 때 App.xaml.cs에 의해 로드됩니다.  
  
    ```csharp  
    if (!rootFrame.Navigate(typeof(GroupedItemsPage), "AllGroups"))  
    {  
        throw new Exception("Failed to create initial page");  
    }  
    ```  
  
     따라서 GroupedItemsPage가 인스턴스화되고 해당 LoadState 메서드가 호출됩니다. LoadState로 인해 정적 SampleDataSource 인스턴스가 생성되고 SampleDataSource 인스턴스는 SampleDataGroup 개체 컬렉션을 만듭니다. 각 SampleDataGroup 개체는 SampleDataItem 개체 컬렉션을 포함합니다. LoadState는 SampleDataGroup 개체 컬렉션을 DefaultViewModel에 저장합니다.  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     그런 다음 DefaultViewModel이 GridView에 바인딩됩니다. 이 바인딩은 데이터 바인딩을 구성할 때 GroupedItemsPage.xaml 파일에서 참조됩니다.  
  
    ```xaml
    <CollectionViewSource  
                x:Name="groupedItemsViewSource"  
                Source="{Binding Groups}"  
                IsSourceGrouped="true"  
                ItemsPath="TopItems"  
                d:Source="{Binding AllGroups, Source={d:DesignInstance Type=data:SampleDataSource, IsDesignTimeCreatable=True}}"/>  
    ```  
  
     CollectionViewSource는 그룹화된 컬렉션 처리를 위한 프록시로 사용됩니다. 바인딩이 수행될 때 CollectionViewSource는 SampleDataGroup 개체 컬렉션을 반복하여 GridView를 채웁니다.  ItemsPath 특성은 각 SampleDataGroup 개체가 포함하는 SampleDataItems 항목을 찾기 위해 사용할 SampleDataGroup 개체 속성을 CollectionViewSource에 알려 줍니다. 이 예에서는 각 SampleDataGroup 개체가 SampleDataItem 개체의 TopItems 컬렉션을 포함하고 있습니다.  
  
     Netflix 응용 프로그램에서는 영화가 장르별로 그룹화됩니다. 따라서 응용 프로그램에 수많은 장르와 해당 장르의 영화 목록이 표시됩니다.  
  
#### <a name="add-a-service-reference-to-the-netflix-odata-service"></a>Netflix OData Service에 대한 서비스 참조 추가  
  
1.  Netflix OData Service를 호출하려면 서비스 참조를 추가해야 합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 서비스 참조 추가...를 선택합니다.  
  
     ![서비스 참조 추가 대화 상자](../../../../docs/framework/data/wcf/media/addservicereferenceodata.png "AddServiceReferenceOData")  
  
2.  주소 표시줄에 Netflix OData Service의 URL을 입력하고 이동을 클릭합니다. Netflix에 대한 서비스 참조 네임스페이스를 설정하고 확인을 클릭합니다.  
  
     ![서비스 참조 추가 오류](../../../../docs/framework/data/wcf/media/addservicereferenceerror.png "AddServiceReferenceError")  
  
    > [!NOTE]
    >  아직 설치 하지 않은 경우 [WCF 데이터 서비스 도구 Windows 스토어 앱 용](http://go.microsoft.com/fwlink/p/?LinkId=266652)을 위와 같은 메시지와 함께 나타납니다. 계속하려면 링크에 표시된 도구를 다운로드하여 설치해야 합니다.  
  
 서비스 참조를 추가하면 WCF Data Services가 Netflix OData Service에서 반환한 OData를 분석하는 데 사용하는 강력한 형식의 클래스가 생성됩니다. SampleDataSource.cs에 정의된 클래스는 GridView에 바인딩될 수 있으므로 생성된 OData 클라이언트 클래스의 데이터를 SampleDataSource.cs에 정의된 바인딩 가능한 클래스로 전송해야 합니다.  이렇게 하려면 SampleDataSource.cs에 정의된 데이터 모델을 변경해야 합니다.  
  
#### <a name="update-the-data-model-for-the-application"></a>응용 프로그램에 맞게 데이터 모델 업데이트  
  
1.  SampleDataSource.cs의 기존 코드에서 코드로 대체 [이 요점](https://gist.github.com/3419288)합니다. 업데이트된 코드는 Netflix OData Service에 대해 쿼리를 수행하는 LoadMovies 메서드를 SampleDataSource 클래스에 추가하고 장르 목록(allGroups) 및 각 장르의 영화 목록을 생성합니다. SampleDataGroup 클래스는 장르를 나타내는 데 사용되고 SampleDataItem 클래스는 영화를 나타내는 데 사용됩니다.  
  
    ```csharp  
    public static async void LoadMovies()  
    {  
        IEnumerable<Title> titles = await ((DataServiceQuery<Title>)Context.Titles  
            .Expand("Genres,AudioFormats,AudioFormats/Language,Awards,Cast")  
            .Where(t => t.Rating == "PG")  
            .OrderByDescending(t => t.ReleaseYear)  
            .Take(300)).ExecuteAsync();  
  
        foreach (Title title in titles)  
        {  
            foreach (Genre netflixGenre in title.Genres)  
            {  
                SampleDataGroup genre = GetGroup(netflixGenre.Name);  
                if (genre == null)  
                {  
                    genre = new SampleDataGroup(netflixGenre.Name, netflixGenre.Name, String.Empty, title.BoxArt.LargeUrl, String.Empty);  
                    Instance.AllGroups.Add(genre);  
                }  
                var content = new StringBuilder();  
                // Write additional things to content here if you want them to display in the item detail.  
                genre.Items.Add(new SampleDataItem(title.Id, title.Name, String.Format("{0}rnrn{1} ({2})", title.Synopsis, title.Rating, title.ReleaseYear), title.BoxArt.HighDefinitionUrl ?? title.BoxArt.LargeUrl, "Description", content.ToString()));  
            }  
        }  
    }  
    ```  
  
     [작업 기반 비동기 패턴](http://go.microsoft.com/fwlink/p/?LinkId=266651) (TAP) 하는 데 비동기적으로 가져오기 300 (Take) 최신 (OrderByDescending) PG 등급 (Where) 영화 Netflix에서 합니다. 코드의 나머지 부분은 OData 피드에 반환된 엔터티에서 SimpleDataItems 및 SimpleDataGroups를 생성합니다.  
  
     또한 SampleDataSource 클래스는 단순 검색 메서드를 구현합니다. 이 예에서는 단순 메모리 내 검색으로 로드된 영화를 검색합니다.  
  
    ```csharp  
    public static IEnumerable<SampleDataItem> Search(string searchString)  
    {  
            var regex = new Regex(searchString, RegexOptions.CultureInvariant | RegexOptions.IgnoreCase | RegexOptions.IgnorePatternWhitespace);  
            return Instance.AllGroups  
                .SelectMany(g => g.Items)  
                .Where(m => regex.IsMatch(m.Title) || regex.IsMatch(m.Subtitle))  
                    .Distinct(new SampleDataItemComparer());  
    }  
    ```  
  
     SampleDataSource.cs에는 ExtensionMethods라는 클래스도 정의되어 있습니다. 이러한 각 확장 메서드는 TAP 패턴을 사용하여 SampleDataSource가 UI를 차단하지 않고 OData 쿼리를 실행할 수 있도록 합니다. 예를 들어 다음 코드에서는 Task.Factory.FromAsync 메서드를 사용하여 TAP를 구현합니다.  
  
    ```csharp  
    public static async Task<IEnumerable<T>> ExecuteAsync<T>(this DataServiceQuery<T> query)  
    {  
        return await Task.Factory.FromAsync<IEnumerable<T>>(query.BeginExecute(null, null), query.EndExecute);  
    }  
    ```  
  
     기본 응용 프로그램과 마찬가지로 응용 프로그램의 기본 페이지는 GroupedItemsPage입니다. 하지만 현재는 Netflix에서 검색된 영화가 장르별로 그룹화된 상태로 표시됩니다.  GroupedItemsPage가 인스턴스화될 때 해당 LoadState 메서드가 호출됩니다. 앞에서 설명한 대로 LoadState로 인해 정적 SampleDataSource 인스턴스가 생성되고 Netflix OData Service가 호출됩니다. LoadState는 장르(SampleDataGroup 개체) 컬렉션을 DefaultViewModel에 저장합니다.  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     그런 다음에는 앞에서 설명한 대로 DefaultViewModel을 사용하여 데이터가 GridView에 바인딩됩니다.  
  
#### <a name="add-a-search-contract-to-allow-the-application-to-participate-in-windows-search"></a>응용 프로그램이 Windows 검색에 참가할 수 있도록 검색 계약 추가  
  
1.  응용 프로그램에 검색 계약을 추가합니다. 이렇게 하면 응용 프로그램이 Windows 8 검색 환경에 통합됩니다. 검색 계약 이름을 SearchResultsPage.xaml로 지정합니다.  
  
     ![검색 계약 추가](../../../../docs/framework/data/wcf/media/addsearchcontract.png "AddSearchContract")  
  
2.  SearchResultsPage.xaml.cs의 58번째 줄에서 queryText를 묶는 따옴표를 제거하여 줄을 수정합니다.  
  
    ```csharp  
    // Communicate results through the view model  
    this.DefaultViewModel["QueryText"] = queryText;  
    this.DefaultViewModel["Filters"] = filterList;  
    this.DefaultViewModel["ShowFilters"] = filterList.Count > 1;  
    ```  
  
3.  SearchResultsPage.xaml.cs의 81번째 줄에 다음 두 코드 줄을 삽입하여 검색 결과를 검색합니다.  
  
    ```csharp  
    // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                    //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                    var searchValue = (string)this.DefaultViewModel["QueryText"];  
                    this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
    ```  
  
 사용자는 Windows 검색을 실행할 때 검색 용어를 입력한 다음 검색 표시줄에서 Netflix Demo 응용 프로그램 아이콘을 터치합니다. 그러면 SearchResultsPage의 LoadState 메서드가 실행됩니다. LoadState로 전송된 탐색 매개 변수에 쿼리 텍스트가 포함됩니다. 그 다음에는 Filter_SelectionChanged 메서드가 호출되고 이 메서드는 SampleDataSource 클래스에 대해 Search 메서드를 호출합니다. SearchResultsPage.xaml 페이지에 결과가 반환되고 표시됩니다.  
  
```csharp  
/// <summary>  
        /// Invoked when a filter is selected using the ComboBox in snapped view state.  
        /// </summary>  
        /// <param name="sender">The ComboBox instance.</param>  
        /// <param name="e">Event data describing how the selected filter was changed.</param>  
        void Filter_SelectionChanged(object sender, SelectionChangedEventArgs e)  
        {  
            // Determine what filter was selected  
            var selectedFilter = e.AddedItems.FirstOrDefault() as Filter;  
            if (selectedFilter != null)  
            {  
                // Mirror the results into the corresponding Filter object to allow the  
                // RadioButton representation used when not snapped to reflect the change  
                selectedFilter.Active = true;  
  
                // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                var searchValue = (string)this.DefaultViewModel["QueryText"];  
                this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
  
                // Ensure results are found  
                object results;  
                ICollection resultsCollection;  
                if (this.DefaultViewModel.TryGetValue("Results", out results) &&  
                    (resultsCollection = results as ICollection) != null &&  
                    resultsCollection.Count != 0)  
                {  
                    VisualStateManager.GoToState(this, "ResultsFound", true);  
                    return;  
                }  
            }  
  
            // Display informational text when there are no search results.  
            VisualStateManager.GoToState(this, "NoResultsFound", true);  
        }  
```  
  
 에 응용 프로그램 참조 검색을 통합에 대 한 자세한 내용은 [검색: Windows 8 검색 환경에 통합](http://go.microsoft.com/fwlink/p/?LinkId=266650)합니다.  
  
## <a name="run-the-application"></a>응용 프로그램 실행  
 F5 키를 눌러 응용 프로그램을 시작합니다. 응용 프로그램을 시작할 때 이미지를 로드하는 데 몇 초 정도 걸릴 수 있습니다. 또한 첫 번째 검색에서는 결과가 반환되지 않을 수 있습니다. 실제 응용 프로그램에서는 이 두 문제를 모두 처리할 수 있습니다.  
  
 응용 프로그램에서 Netflix OData Service를 호출하고, 생성된 OData 클라이언트 클래스의 데이터를 받은 다음 해당 데이터를 바인딩 가능한 데이터 클래스(SampleDataSource, SampleDataGroup 및 SampleDataItem)로 전송합니다. 응용 프로그램에서는 이러한 바인딩 가능한 클래스를 사용하여 데이터를 GridView에 바인딩합니다. XAML 데이터 바인딩의 참조를 작동 하는 방법을 모르는 경우 [항목 목록 또는 표 (C# /vb/c + + 및 XAML을 사용 하 여 Windows 스토어 앱)을 그룹화 하는 방법을](http://msdn.microsoft.com/library/windows/apps/xaml/hh780627)합니다.
