
# MVVM + Coordinator Pattern

Coordinator 패턴을 적용하는 경우 기능(Feature 또는 Business) 단위로 Model, ViewModel, Controller를 함께 관리하는 구조를 선호합니다.

```text
Classes/
├── Coordinator/
│   └── Coordinators/
│
└── Scenes/
    ├── FeatureA/
    │   ├── Model/
    │   ├── ViewModel/
    │   └── Controller/
    │
    └── FeatureB/
        ├── Model/
        ├── ViewModel/
        └── Controller/
```

이 구조는 기능별 응집도를 높이고 관련 코드의 탐색 및 유지보수를 쉽게 하는 데 목적
