---
layout: post
title:  "Adding Multiple Categories in Posts"
summary: "Learn how to add categories in posts"
author: ssh
date: '2021-02-28 1:35:23 +0530'
category: ['jekyll','guides', 'sample_category']
tags: jekyll
thumbnail: /assets/img/posts/code.jpg
keywords: devlopr jekyll, how to use devlopr, devlopr, how to use devlopr-jekyll, devlopr-jekyll tutorial,best jekyll themes, multi categories and tags
usemathjax: false
permalink: /blog/adding-categories-tags-in-posts/


questions:
  - question: "Q1. 애플리케이션을 실행하기 위해 DevOps 엔지니어는 퍼블릭 서브넷에서 퍼블릭 IP 주소로 Amazon EC2 인스턴스를 시작합니다. 사용자 데이터 스크립트는 애플리케이션 아티팩트를 가져와 시작시 인스턴스에 설치합니다. 이제 애플리케이션의 보안 분류를 변경하려면 인스턴스가 인터넷에 액세스하지 않고 실행되어야합니다. 인스턴스가 성공적으로 시작되고 정상으로 표시되지만 애플리케이션이 설치되지 않은 것 같습니다. 다음 중 새 규칙을 준수하면서 애플리케이션을 성공적으로 설치해야하는 것은 무엇입니까?"
    answers:
      - A. 탄력적 IP 주소가 연결된 퍼블릭 서브넷에서 인스턴스를 시작합니다. 애플리케이션이 설치되고 실행되면 나중에 스크립트를 실행하여 탄력적 IP 주소 연결을 해제합니다.
      - B. NAT 게이트웨이를 설정합니다. 프라이빗 서브넷에 EC2 인스턴스를 배포합니다. NAT 게이트웨이를 기본 경로로 사용하도록 프라이빗 서브넷의 라우팅 테이블을 업데이트합니다.
      - C. Amazon S3 버킷에 애플리케이션 아티팩트를 게시하고 S3 용 VPC 엔드 포인트를 생성합니다. S3 버킷에서 애플리케이션 아티팩트를 읽을 수 있도록 EC2 인스턴스에 IAM 인스턴스 프로파일을 할당합니다.
      - D. 애플리케이션 인스턴스에 대한 보안 그룹을 생성하고 아티팩트 리포지토리에 대한 아웃 바운드 트래픽 만 허용 목록에 추가합니다. 설치가 완료되면 보안 그룹 규칙을 제거합니다.
    answerNum: C
    description: VPC 엔드포인트 생성
    questionNum: 1
    

---

## Adding Multiple Categories in Posts

To add categories in blog posts all you have to do is add a **category** key with category values in frontmatter of the post :

```yml
---
category: ['jekyll', 'guides', 'sample_category']
---
```

Then to render this category using link and pages. All we need to do is,

1. Create a new file with [your_category_name].md inside categories folder.

2. Copy categories/sample_category.md file and replace the content in [your_category_name].md in that. (Please don't copy the code below its just sample, since it renders the jekyll syntax dynamically)

```jsx
---
layout: page
title: Guides
permalink: /blog/categories/your_category_name/
---

<h5> Posts by Category : {{ page.title }} </h5>

<div class="card">
{% for post in site.categories.your_category_name %}
 <li class="category-posts"><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</div>
```


Using the category, all the posts associated with the category will be listed on
`http://localhost:4000/blog/categories/your_category_name`



{% include question_box.html %}

