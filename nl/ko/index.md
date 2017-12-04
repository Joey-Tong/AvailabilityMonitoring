---

copyright:
  years: 2015, 2017
lastupdated: "2017-11-07"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}

# Availability Monitoring 시작하기
{: #avmon_gettingstarted}

{{site.data.keyword.prf_hublong}}을 사용하면 24시간 내내 전세계 모든 위치에서 시뮬레이션된 성능 테스트를 실행할 수 있습니다. 사용자에게 영향을 주기 전에 성능 문제점을 사전에 발견, 분리 및 진단하십시오. 애플리케이션이 사용 가능하며 지속적인 업데이트를 롤아웃할 때 응답 시간 목표를 충족하는지 확인하십시오. 사용자 트랜잭션 데이터를 수집할 수 있도록 애플리케이션의 데이터 콜렉터를 구성하십시오. {{site.data.keyword.prf_hubshort}}에서 이 데이터를 사용하여 애플리케이션의 응답성과 처리량을 모니터할 수 있습니다.
{: shortdesc}

## 이 태스크에 대한 정보
{: #avmon_start_about}

{{site.data.keyword.prf_hubshort}}은 {{site.data.keyword.Bluemix_notm}} 카탈로그에서 DevOps 도메인의 서비스로 사용 가능합니다. 이는 또한 **모니터링** 탭의 애플리케이션 대시보드에서 기본적으로 사용 가능합니다. 애플리케이션 가용성 및 성능에 대한 모니터링을 바로 시작할 수 있습니다. {{site.data.keyword.prf_hubshort}}을 애플리케이션에 바인드하면 기본적으로 기본 애플리케이션 URL을 모니터하기 위해 합성 테스트가 자동으로 작성됩니다. 

## 웹 페이지 테스트 작성
{: #avmon_start_procedure}

다음 단계를 완료하여 애플리케이션에 대한 {{site.data.keyword.prf_hubshort}}을 열고, 다른 URL을 모니터하기 위한 웹 페이지 테스트를 작성하며, 테스트에 대한 알림 경보를 설정하십시오. 

1.  모니터할 Cloud Foundry 애플리케이션이 있는 경우에는 **앱** 대시보드의 **모든 애플리케이션** 테이블에서 애플리케이션 이름을 클릭하십시오. 아직 애플리케이션이 없는 경우에는 이를 작성하십시오. 애플리케이션 카드가 자동으로 열립니다. 모니터링 탭을 클릭하면 Cloud Foundry 애플리케이션이 {{site.data.keyword.prf_hubshort}}과 자동으로 바인딩됩니다. 
2.  {{site.data.keyword.prf_hubshort}}을 열려면 **모니터링** 탭을 클릭하십시오. **모니터링** 탭은 마지막 24시간의 **평균 테스트 가용성**, **현재 테스트 상태**, 현재 플랜 할당의 **사용량**을 보여주는 세 개의 게이지를 표시합니다. **새 테스트 추가**를 클릭하여 모니터링 테스트를 구성하십시오.

    ![Availability Monitoring 탭](images/avmon_tab.png)

    기본 애플리케이션 URL은 기본적으로 모니터링됩니다. 모니터링하는 기타 URL 및 서비스는 Bluemix 내부 또는 외부에 있을 수 있으며 연관된 Cloud Foundry 애플리케이션과 관련될 필요는 없습니다. 

3.  모니터링 설정 페이지에서 **단일 조치**를 클릭한 후에 단일 조치 페이지에서 **웹 페이지**를 클릭하십시오. 
4.  **이름** 필드에 테스트의 이름을 입력하십시오. **설명** 필드에 테스트 목적이라는 설명을 추가하십시오. 
5.  테스트할 웹 애플리케이션의 **URL**을 입력하십시오. 
6.  응답 유효성 검증 섹션에서 테스트에 대한 경고 및 위험 경보 임계값을 구성하십시오. 각 행에 대한 **값** 및 **단위**를 편집하십시오. 경고 및 위험 임계값을 초과하는 응답 시간은 경보를 트리거합니다. 

    ![기본 경고 및 위험 임계값의 응답 유효성 검증 섹션.](images/avmon_webpage_resp_val.png)

7.  **블랙리스트** 및 **화이트리스트**를 사용하여 요청이 전송될 대상 URL 및 도메인과 애플리케이션 테스트의 메트릭과 상태에 컨트리뷰션하는 URL 및 도메인을 판별할 수 있습니다. **화이트리스트** 및 **블랙리스트**에 대해 포함 또는 차단할 URL 및 도메인을 추가하십시오. 블로킹 및 필터링에 대한 자세한 정보는 [화이트리스트 및 블랙리스트에서 블로킹 및 필터링](avmon_whitelist_blacklist.html "화이트리스트 및 블랙리스트를 사용하여 요청을 전송할 대상 리소스 및 애플리케이션 테스트의 메트릭과 상태에 컨트리뷰션하는 리소스를 판별할 수 있습니다. 화이트리스트 및 블랙리스트는 웹 페이지 및 스크립팅된 동작 테스트에만 사용 가능합니다.")을 참조하십시오. 
8.  **검증**을 클릭하여 웹 페이지 테스트를 작성하고 테스트 요청이 올바른지 판별하십시오. 

    {{site.data.keyword.prf_hubshort}}는 테스트 URL에 GET 요청을 전송하여 테스트 유효성을 판별합니다. 테스트 확인 중에는 응답 유효성 검증이 발생하지 않습니다. 

    유효성이 검증된 테스트는 검증된 항목 테이블에 표시됩니다. 3 - 8단계를 반복하여 URL을 더 추가할 수 있습니다. 

9.  테스트 설정을 구성하려면 **다음**을 클릭하십시오. 

    테스트 구성의 요약이 표시됩니다. 예를 들어 다음 메시지가 기본 설정에 표시됩니다. 

    `테스트 발생 예정: 테스트가 지정된 임계값을 초과하는지 판별하기 위해 세 개의 위치에서 동시에 15분마다`

    월별 예상 테스트 수 및 예상 사용량이 현재 테스트 구성을 기반으로 표시됩니다.

10. 설정 분할창에서 **편집**을 클릭하여 테스트에 대한 현재 설정을 표시하십시오. 다음 설정을 업데이트할 수 있습니다. 
    - **간격**은 테스트의 실행 빈도를 정의합니다. 
    - **테스트 빈도**는 테스트가 동시에 모든 위치에서 실행되는지 또는 각각의 간격에 다른 위치에서 실행되는지를 판별합니다. 모든 위치에서 동시에 테스트를 실행하려면 **동시**를 선택하고 선택된 다른 위치에서 다른 간격으로 테스트를 실행하려면 **시차**를 선택하십시오. 
    - **위치**는 테스트가 실행될 위치를 판별합니다. 

    **저장**을 클릭하여 테스트 구성을 완료하십시오.

11. **완료**를 클릭하십시오. {{site.data.keyword.prf_hubshort}} 대시보드에는 전체 테스트의 요약, 경보의 위치와 빈도를 나타내는 맵과 테이블, 애플리케이션과 연관된 모든 합성 테스트, 활동의 테이블, 그리고 애플리케이션 및 기타 웹 사이트의 응답 시간과 가용성을 보여주는 선형 그래프가 표시됩니다. 필요에 따라 추가 테스트를 작성할 수 있습니다.
12. {{site.data.keyword.alertnotificationfull}} 서비스를 사용하여 이벤트가 발생하면 알림을 보내도록 모니터링 기능을 구성할 수 있습니다. 자세한 정보는 [알림 사용](avmon_notifications.html "이벤트가 발생하면 알림을 보내도록 모니터링 기능을 구성합니다.")을 참조하십시오. 

## 결과
{: #avmon_getstarted_results}

테스트 결과는 테스트에서 지정한 간격이 경과한 후에 표시됩니다. 기본 간격은 15분입니다.

이제 웹 애플리케이션의 가용성을 모니터할 준비가 되었습니다. 애플리케이션, 웹 사이트 또는 REST API에 대한 응답 시간 및 가용성 정보는 **응답 시간 및 가용성** 분할창에서 최근 활동 및 테스트에 대한 정보와 함께 선형 그래프에 표시됩니다. 

{{site.data.keyword.prf_hubshort}}의 기능에 대해 알아보는 데 도움이 되는 두 개의 안내서를 사용할 수 있습니다. 

 - **동영상 튜토리얼 라이브러리** - 동영상 튜토리얼 라이브러리에는 Bluemix 애플리케이션 작성, Availability Monitoring 테스트 작성, Selenium IDE에서 테스트 스크립트 작성 및 Slack에 경보 전송을 수행하는 방법에 대한 동영상이 포함되어 있습니다. 
 - **모니터링 시작!** - 모니터링 시작 안내서는 대시보드의 영역을 강조표시하며 {{site.data.keyword.prf_hubshort}}의 각 기능을 설명합니다. 

안내서를 열려면 **도움말** 아이콘 ![도움말 아이콘](images/help_icn_white_sml.jpg)을 클릭한 후에 보려는 안내서를 클릭하십시오. 