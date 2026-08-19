---
layout: post
title: "GitHub Copilot 멀티 에이전트 바이브 코딩 워크숍 프록터 참여 후기"
date: 2026-08-19 10:00:00 +0900
categories:
  - GitHub
  - Copilot
tags:
  - GitHub Copilot
  - Multi-Agent
  - Vibe Coding
  - Workshop
---

이번에 **GitHub Copilot을 활용한 멀티 에이전트 바이브 코딩 워크숍**에 프록터(Proctor)로 참여했습니다.
최근 GitHub Copilot을 공부하고 교육이나 발표를 준비하면서 GitHub 관련 활동에 조금씩 참여하고 있는데요.
이번에는 참가자가 아니라 **워크숍 진행을 지원하는 프록터**로 참여하게 되었습니다.

워크숍 안내는 [Ticketa 이벤트 페이지](https://ticketa.co/event/c99wxzdg)에서, 실습 자료는 [급식배틀 워크숍 GitHub 저장소](https://github.com/devkimchi/battle-school-lunch-workshop)에서 확인할 수 있습니다.

<figure class="post-figure">
  <img src="{{ '/assets/images/posts/github-copilot-multi-agent-workshop/workshop-overview.jpg' | relative_url }}" alt="참가자들이 GitHub Copilot 실습을 진행하는 워크숍 현장">
  <figcaption>GitHub Copilot 멀티 에이전트 바이브 코딩 워크숍 현장</figcaption>
</figure>

## 멀티 에이전트 바이브 코딩 워크숍

이번 워크숍에서는 GitHub Copilot을 활용해 실제 애플리케이션을 개발하면서 **AI와 협업하는 개발 방식**을 직접 경험해보는 시간을 가졌습니다.
실습 프로젝트는 **'급식배틀'**로, 초·중·고등학교의 급식 메뉴를 조회하고 분석하는 애플리케이션을 만들어보는 방식으로 진행되었습니다.

처음부터 바로 개발에 들어가는 것이 아니라, 바이브 코딩을 하기 위해 필요한 개념과 준비 과정부터 하나씩 살펴보았습니다.

<figure class="post-figure">
  <img src="{{ '/assets/images/posts/github-copilot-multi-agent-workshop/aspire-presentation.jpg' | relative_url }}" alt="Aspire를 소개하는 워크숍 발표 현장">
  <figcaption>Aspire와 개발 인프라에 대한 설명</figcaption>
</figure>

전체적인 진행 순서는 다음과 같았습니다.

1. 사다리 게임을 통한 팀 구성
2. 바이브 코딩에 대한 전반적인 설명
3. 데모 소개
4. AI 개발 핵심 내용 정리
5. 팀별 개발 시작

## 바이브 코딩, 그냥 AI에게 코드를 만들어달라고 하는 것일까?

이번 워크숍에서 특히 인상적이었던 부분은 **AI에게 단순히 코드를 생성하도록 요청하는 것과 AI와 함께 개발하는 것은 다르다**는 점이었습니다.

본격적인 개발에 앞서 MCP와 Aspire에 대해 살펴보고, AI가 프로젝트를 이해하고 원하는 방향으로 개발할 수 있도록 필요한 문서들을 준비했습니다.
대표적으로 사용한 문서는 다음 세 가지였습니다.

- **AGENTS.md**: GitHub Copilot이 프로젝트에서 어떻게 행동해야 하는지를 정의합니다. 꼭 지켜야 하는 것, 해도 되는 것, 하면 안 되는 것 등을 명확하게 작성해 AI가 작업할 수 있는 범위를 설정합니다.
- **PRD.md**: 어떤 제품을 만들 것인지, 어떤 기능이 필요한지를 정리하는 제품 요구사항 문서입니다.
- **TRD.md**: 프로젝트에서 사용할 기술 스택과 기술적인 요구사항을 정리합니다.

결국 바이브 코딩에서도 중요한 것은 단순히 좋은 프롬프트 하나를 작성하는 것이 아니라, **AI가 프로젝트를 제대로 이해하고 작업할 수 있는 컨텍스트와 기준을 만들어주는 것**이라는 점을 다시 느낄 수 있었습니다.

<figure class="post-figure">
  <img src="{{ '/assets/images/posts/github-copilot-multi-agent-workshop/agent-development-layers.jpg' | relative_url }}" alt="AI, 도구, 인프라로 구성된 에이전트 개발의 세 가지 계층">
  <figcaption>AI·LLM, 도구, 인프라로 구성된 에이전트 개발의 세 가지 계층</figcaption>
</figure>

## 본격적인 개발 시작

개념 설명과 데모가 끝난 뒤에는 각 팀이 직접 개발을 시작했습니다.
GitHub Copilot을 활용해 요구사항을 분석하고 코드를 생성하면서 각자의 애플리케이션을 만들어 나갔습니다.

저는 이때 프록터로서 참가자분들이 실습을 진행하다가 문제가 생기거나 막히는 부분이 있을 때 함께 확인하고 해결하는 역할을 맡았습니다.

<figure class="post-figure">
  <img src="{{ '/assets/images/posts/github-copilot-multi-agent-workshop/team-development.jpg' | relative_url }}" alt="급식배틀 애플리케이션을 개발하는 참가자들">
  <figcaption>GitHub Copilot과 함께 급식배틀 애플리케이션을 개발하는 모습</figcaption>
</figure>

같은 실습을 진행하고 있어도 개발 환경이나 진행 상황에 따라 발생하는 문제가 조금씩 달랐기 때문에, 저에게도 다양한 상황을 직접 접하고 해결해볼 수 있는 경험이었습니다.

## 알려주는 과정에서 더 많이 배우게 된 시간

이번에 프록터로 참여하면서 가장 크게 느낀 점 중 하나는 **'알고 있는 것'과 '다른 사람에게 설명할 수 있는 것'은 다르다**는 것이었습니다.
내가 직접 개발할 때는 자연스럽게 넘어갔던 부분도 누군가에게 설명하려면 다음 질문을 다시 생각하게 됩니다.

> 왜 이렇게 해야 하지?
>
> 지금 어떤 문제가 발생한 거지?
>
> 어떻게 설명해야 가장 이해하기 쉬울까?

특히 여러 참가자의 서로 다른 문제를 짧은 시간 안에 파악하고 해결해야 했기 때문에 저 역시 많이 공부할 수 있었던 시간이었습니다.

## GitHub를 더 깊게 알아가는 중

최근 GitHub Copilot을 공부하면서 교육, 발표, 워크숍 등 GitHub와 관련된 다양한 경험을 조금씩 쌓아가고 있습니다.
처음에는 단순히 개발할 때 사용하는 도구 중 하나로 GitHub를 바라봤다면, 공부할수록 GitHub Actions, Copilot, MCP, Agent를 비롯해 개발 과정 전반에서 활용할 수 있는 영역이 정말 많다는 것을 느끼고 있습니다.

이번 워크숍 역시 그중 하나를 직접 경험해볼 수 있었던 좋은 기회였습니다.
앞으로도 GitHub와 AI 기반 개발 방식에 대해 꾸준히 공부하고 직접 사용해보면서, 단순히 기술을 사용하는 것을 넘어 **다른 사람에게 설명하고 경험을 공유할 수 있을 정도로 깊이 이해하는 것**을 목표로 해보려고 합니다.

이번 워크숍에서 만난 다양한 질문과 문제들도 앞으로 더 공부해야 할 부분을 발견할 수 있었던 좋은 계기가 된 것 같습니다.
좋은 워크숍을 준비해주신 분들과 함께 참여해주신 모든 분들께 감사드립니다.

다음에는 또 어떤 GitHub 관련 경험을 하게 될지 기대해봅니다.
