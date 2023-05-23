---
title: aws_security_group
post-order: 1
sidebar:
  nav: hashicorp
---

## 1. AWS Provider 정의

 [AWS Provider](http://kim-dongoh.github.io/documents/hashicorp/terraform/provider/aws/) 참조



## 2. Data Source 정의

> [aws_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/security_group)

이름이 `default`이며 `tags.Name` 항목이 `default`인 보안 그룹을 찾아 해당 보안 그룹의 속성들을 참조 가능하게 함

```bash
vi main.tf
```

```hcl
data "<Data Source Type>" "<Data Source Name>" {
  name = "default"
  tags = {
    Name = "default"
  }
}
```

* `Data Source Type`: `aws_security_group`
  * AWS Provider에 정의된 값
  * `Data Source Type` 목록은 [AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs) 페이지에서 좌측 사이드 바에 검색하면 `Data Sources` 하위 항목으로 출력
* `Data Source Name`: 해당 Data Source의 이름을 정의
* `name`: 이름이 `default`인 보안 그룹을 지정
* `tags.Name`: 태그값을 참조하여 태그가 `Name: default`인 보안 그룹을 지정
