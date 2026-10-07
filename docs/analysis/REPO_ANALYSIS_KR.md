# Awesome LLM Apps — 전수조사 분석 및 활용·수익화 가이드 (한국어)

> 이 문서는 저장소 전체(파일 1,887개 / 170MB)를 실제로 열어 조사한 결과를 정리한 것입니다.
> 추측이 아니라 **실측값 + 실제 코드 인용** 기반입니다.

## 📎 저장소 주소

| 구분 | URL |
|---|---|
| **내 저장소 (포크)** | https://github.com/bmshin94/awesome-llm-apps |
| **원본 저장소** | https://github.com/Shubhamsaboo/awesome-llm-apps |
| 라이선스 | [Apache-2.0](https://github.com/bmshin94/awesome-llm-apps/blob/main/LICENSE) |
| 공식 튜토리얼 사이트 | https://www.theunwindai.com |
| 스킬 설치 CLI | https://skills.sh · https://agentskills.io |

- **분석 기준 커밋**: `4f952d374ed0ef27da0c25de992148f9bd2031ef` (`4f952d3`)
- **분석 일자**: 2026-10-07
- ⚠️ 저장소는 주간 단위로 업데이트됩니다. 영상·강의·문서로 재가공할 때는 **위 커밋 해시를 고정 기준**으로 명시하세요.

---

# 1. 이게 뭐하는 저장소인가

## 한 줄 정의

> **"실행되는 AI 앱 182개가 들어있는 오픈소스 레시피 창고"**

라이브러리나 프레임워크가 **아닙니다**. `pip install`로 쓰는 패키지가 아니라 **복사해서 내 걸로 만드는 완성된 예제 코드 모음**입니다.
루트에 `requirements.txt`나 `package.json`이 **없습니다** → "저장소 전체 설치"라는 개념이 존재하지 않습니다.

## 실측 통계

| 항목 | 값 |
|---|---|
| 전체 파일 수 | 1,887개 |
| 용량 | 170MB |
| 독립 실행 프로젝트 | **182개** |
| Python 파일 | 546개 |
| React/TypeScript | 313개 (tsx 212 + ts 101) |
| README(문서) | **287개** — 프로젝트마다 설명서 존재 |
| 라이선스 | Apache-2.0 (상업적 이용·판매 가능) |
| 외부 평가 | Trendshift 일간 1위 저장소 선정 |

## 10개 대분류 — 폴더별 내용

| 폴더 | 개수 | 내용 |
|---|---|---|
| `starter_ai_agents/` | 17 | API 키 하나로 돌아가는 단일 파일 에이전트 (입문용) |
| `advanced_ai_agents/` | **55** | 도구+메모리+다단계 추론. 최대 규모 |
| `agent_skills/` | 9 | ⭐ 코딩 에이전트에 능력을 심는 스킬 (가장 최신) |
| `rag_tutorials/` | 25 | RAG 커리큘럼. 쉬운 것 → 어려운 것 순 |
| `mcp_ai_agents/` | 7 | MCP로 외부 도구 연결 |
| `generative_ui_agents/` | 18 | ⭐ 유일한 React/Next.js 폴더 |
| `ai_agent_framework_crash_course/` | 28챕터 | 번호순 정규 강의 (ADK 9 + OpenAI SDK 11) |
| `voice_ai_agents/` | 4 | 음성 입출력 |
| `always_on_agents/` | 2 | ⭐ 스케줄로 알아서 도는 백그라운드 에이전트 |
| `advanced_llm_apps/` | 27 | 메모리·비용절감·파인튜닝·Chat with X |

### `advanced_ai_agents/` 세부
- `single_agent_apps/` (18) — 딥리서치, 사기조사, 재무코치, 영화제작, 실적발표 분석, 시스템 아키텍트(DeepSeek R1+Claude)
- `multi_agent_apps/` (20) — 집 리모델링(사진→포토리얼 렌더), VC 투자심사팀, 법률팀, 채용팀, 부동산팀, CrewAI 디지털 에이전시
- `autonomous_game_playing_agent_apps/` (3) — 체스/틱택토 AI 대결, PyGame 코드 자동생성

### `rag_tutorials/` 학습 경로
```
rag_chain (기본) → autonomous_rag → corrective_rag (자기채점·재시도)
→ hybrid_search_rag → agentic_rag_* (5종) → multimodal_agentic_rag
→ knowledge_graph_rag_citations → rag_database_routing
→ rag_failure_diagnostics_clinic (내 RAG 왜 틀리나 진단) ⭐
```

### `ai_agent_framework_crash_course/` — 사실상 완성된 강의 목차
**Google ADK (9단계)**: `1_starter_agent` → `2_model_agnostic_agent` → `3_structured_output_agent` → `4_tool_using_agent`(내장/함수/서드파티/MCP 4종) → `5_memory_agent` → `6_callbacks` → `7_plugins` → `8_simple_multi_agent` → `9_multi_agent_patterns` + `adk_yaml_examples`

**OpenAI Agents SDK (11단계)**: starter → 구조화출력 → 도구 → 실행 → **5 컨텍스트관리** → **6 가드레일/검증** → 세션 → **8 핸드오프/위임** → 멀티에이전트 오케스트레이션 → **10 트레이싱/관측** → 11 음성

> 5·6·10번(컨텍스트/가드레일/관측)은 블로그 자료가 거의 없는 영역이며, 실무에서 에이전트를 망치는 주범입니다.

## 실제 기술 스택 (requirements.txt 182개 전수 집계)

| 순위 | 라이브러리 | 횟수 | 역할 |
|---|---|---|---|
| 1 | **streamlit** | 74 | 거의 모든 UI. Python만으로 웹앱 |
| 2 | openai | 47 | GPT |
| 3 | python-dotenv | 45 | 키 관리 |
| 4 | **agno** | 44 | ⭐ 이 저장소의 핵심 에이전트 프레임워크 |
| 5 | pydantic | 30 | 구조화 출력 검증 |
| 6 | google-adk | 21 | Google 에이전트 키트 |
| 7 | qdrant-client | 14 | 벡터DB |
| 8 | openai-agents | 12 | OpenAI Agents SDK |
| 9 | fastapi / uvicorn | 12 / 12 | 백엔드 API |
| 10 | ollama | 11 | ⭐ 로컬 무료 모델 |
| - | langchain / langgraph | 9 / 5 | 체인·그래프 |
| - | mem0ai | 8 | 장기 메모리 |
| - | mcp | 6 | MCP 프로토콜 |

**핵심 인사이트**: LangChain 중심이 아니라 **Agno(44) + Streamlit(74)** 조합이 주력. Agno는 LangChain보다 가볍고 빠른 신세대 프레임워크("20줄로 금융 분석가 팀").

## API 키 실태 (전체 코드 grep)

| 키 | 등장 | 비고 |
|---|---|---|
| `OPENAI_API_KEY` | 165 | 가장 많음 (유료) |
| `GOOGLE_API_KEY` | 81 | Gemini (무료 티어 넉넉) |
| `ANTHROPIC_API_KEY` | 25 | Claude |
| `GEMINI_API_KEY` | 20 | |
| `FIRECRAWL_API_KEY` | 20 | 무료 500크레딧/월 |
| `EXA_API_KEY` / `TAVILY_API_KEY` | 18 / 10 | 각 무료 1,000검색/월 |
| `PERPLEXITY_API_KEY` | 8 | 유료 |
| `GITHUB_TOKEN` | 8 | |
| `TOGETHER_API_KEY` | 7 | $1 크레딧 |

## 품질·신뢰도 평가

**좋은 점**
- Apache-2.0 — 포크해서 상업 판매 가능. README 원문: *"Fork it, ship it, sell it."*
- 프로젝트 182개에 README 287개 — 문서화 비율이 비정상적으로 높음
- `agent_skills`는 GitHub Actions CI로 **자동 eval + strict lint** 통과 필수
- 로컬/클라우드 **양쪽 버전을 같이 제공**하는 프로젝트 다수
- 최신성: Gemini 3 Flash, Gemini 3.8 Live, DeepSeek R1, Nano Banana Pro, x402 결제 프로토콜 반영
- README 8개 언어 번역(한국어 포함)
- 보안: 코드에 키 하드코딩 없음 → UI 입력 또는 `.env`

**주의할 점**
- 폴더마다 `requirements.txt`가 따로 → 전체 설치 불가, **프로젝트별 가상환경 필수**
- 의존성 버전 핀 불균일 (`streamlit==1.41.1` vs `streamlit` 무버전) → 충돌 가능
- 170MB 중 상당량이 이미지(jpg 78 + png 56) → 클론 느림 (`--depth 1` 권장)
- 의료영상 분석 등은 **데모용**, 실제 진단 용도 금지
- 품질 편차: `always_on_agents`(유닛테스트+eval 有) ↔ 일부 starter(단일 스크립트)

## 나에게 무슨 도움이 되는가
1. **학습 가속기** — 개념이 아니라 돌아가는 코드로 배움. RAG 25종 순차 학습 시 전문가 수준 지형도 확보
2. **부품 창고** — "PDF 파싱 + 벡터DB + 인용 출처" 같은 패턴을 가져와 조립
3. **아이디어 카탈로그** — 182개 전부 검증된 AI 앱 아이템. 기획 레퍼런스 자체로 가치
4. **즉시 수익화 자산** — Apache-2.0이라 업종 특화 후 판매 가능
5. **내 코딩 에이전트 강화** — `agent_skills` 설치로 오늘부터 생산성 상승
6. **교육 콘텐츠 원석** — README 287개 + 커리큘럼 28챕터가 이미 강의 구조

---

# 2. 핵심 개념 쉽게

## 에이전트란
```
그냥 챗봇:  질문 → [AI] → 답변 (끝)

에이전트:   질문 → [AI] → "검색해야겠다" → 🔍 검색
                    ↓ 결과 봄 → "계산도 필요" → 🧮 계산
                    ↓ 결과 봄 → "됐다" → 답변
```
**차이는 하나: 에이전트는 도구를 직접 쓴다.** 몇 번 쓸지, 뭘 쓸지 스스로 정함.

## RAG란
```
RAG 없음: "우리 회사 휴가 규정?" → "일반적으로 연차는..." ❌ (지어냄)
RAG 있음: 회사 PDF에서 관련 문단 검색 → AI에 같이 전달 → "규정 제3조에 따르면..." ✅
```
**RAG = AI한테 커닝페이퍼 주는 기술.** 기업 AI 프로젝트의 약 80%가 이것. 그래서 25개나 있음.

## 멀티 에이전트란
```
혼자: [만능 AI 1명] → 그럭저럭
팀:   [재무분석가] [시장조사] [리스크평가] → [팀장 AI] → 훨씬 좋은 결과
```
좁은 역할 + 전용 도구를 주면 품질이 확 올라감.

## 스킬이란 ⭐
내 Claude Code / Cursor에 **추가로 가르치는 전문 기술**. 폴더 하나(`SKILL.md` + 스크립트)를 복사하면 끝.
```
⚰️ project-graveyard   → "나 왜 프로젝트 못 끝내?" → PC 스캔 → git 기록으로 사인 분석
🩺 dependency-doctor   → requirements.txt 위험 의존성 자동 진단
🔭 scope-creep-detector → 커밋이 원래 목적보다 커졌는지 자동 판정
```

## 실제 폴더 하나 (파일 4개가 전부)
`starter_ai_agents/ai_travel_agent/`
```
README.MD               설명서
requirements.txt        6줄 (streamlit, agno, openai, ollama, google-search-results, icalendar)
travel_agent.py         클라우드 버전 (OpenAI, 유료)
local_travel_agent.py   로컬 버전 (Ollama, 무료) ⭐
```
단순 챗봇이 아니라 **일정 생성 후 `.ics` 캘린더 파일로 내보내기**까지 구현돼 있음.
→ **이 구조가 182번 반복됩니다. 외울 게 없습니다.**

## 꼭 알아야 할 도구 4개 (전체의 80%)
| 도구 | 설명 |
|---|---|
| Streamlit | Python만으로 웹앱. 프론트엔드 몰라도 됨 |
| Agno | 에이전트 프레임워크. LangChain보다 쉽고 빠름 |
| Ollama | 내 PC에서 AI 실행. **완전 무료, 인터넷 불필요** |
| Qdrant | 벡터DB. RAG의 커닝페이퍼 보관함 |

## "뭐부터 해?" 3단계
```
오늘 (10분)    agent_skills/ 스킬 2~3개 설치 → 0원, 설정 0개, 효과 즉시
이번 주 (2~3h) starter_ai_agents/ai_data_analysis_agent 실행 → CSV 올리고 한국어로 질문
이번 달        rag_tutorials/local_rag_agent (무료)로 내 문서 챗봇
               → 이후 generative_ui_agents/ 로 React 연결
```

---

# 3. 핵심 질문 7개

## Q1. 설치 및 사용법

### 공통 1단계 (1회만)
```bash
git clone https://github.com/bmshin94/awesome-llm-apps.git
cd awesome-llm-apps
# 빠르게: git clone --depth 1 https://github.com/bmshin94/awesome-llm-apps.git
```

### 패턴 A — Python 앱 (약 160개)
```bash
cd starter_ai_agents/ai_data_analysis_agent
python -m venv .venv                  # ⭐ 가상환경 필수
source .venv/bin/activate             # Windows: .venv\Scripts\activate
pip install -r requirements.txt
streamlit run ai_data_analyst.py      # → http://localhost:8501
```
요구사항: Python **3.10+** 권장 (README 기준 3.8+ 19개, 3.10+ 9개, 3.11+ 6개, 3.12 4개)

### 패턴 B — 완전 무료 로컬 (13개, 비용 0원)
```bash
curl -fsSL https://ollama.com/install.sh | sh     # mac/linux (Windows는 ollama.com)
ollama pull llama3.2
cd rag_tutorials/local_rag_agent
pip install -r requirements.txt                   # agno, qdrant-client, ollama, pypdf (4줄)
streamlit run local_rag_agent.py
```
→ 인터넷 끊어도 동작. 비용 0원. 데이터 외부 유출 0.

**로컬(Ollama) 가능 프로젝트 13개**
```
rag_tutorials/local_rag_agent ⭐          rag_tutorials/deepseek_local_rag_agent
rag_tutorials/qwen_local_rag              rag_tutorials/llama3.1_local_rag
rag_tutorials/local_hybrid_search_rag     rag_tutorials/agentic_rag_embedding_gemma
rag_tutorials/knowledge_graph_rag_citations
starter_ai_agents/ai_travel_agent (local_travel_agent.py)
starter_ai_agents/ai_reasoning_agent
advanced_llm_apps/cursor_ai_experiments (local_chatgpt_clone)
advanced_llm_apps/chat-with-tarots
advanced_ai_agents/.../ai_tic_tac_toe_agent
advanced_ai_agents/.../ai_legal_agent_team/local_ai_legal_agent_team
```

### 패턴 C — Agent Skill 설치 (9개) ⭐ 10초
```bash
npx skills add https://github.com/Shubhamsaboo/awesome-llm-apps/tree/main/agent_skills/project-graveyard
```
`skills` CLI가 설치된 에이전트를 자동 감지해 올바른 경로에 배치.

| 에이전트 | 스킬 경로 |
|---|---|
| Claude Code | `~/.claude/skills/` |
| Codex | `~/.codex/skills/` |
| Cursor | `~/.cursor/skills/` |
| Copilot / VS Code | `~/.copilot/skills/` |
| Antigravity | 프로젝트 `.agents/skills/` |
| OpenClaw | `~/.openclaw/skills/` |
| Hermes | `~/.hermes/skills/` |
| **팀 공유** | 레포 `.agents/skills/` (Claude Code는 `.claude/skills/`) |

사용은 설정이 아니라 **말로**: "나 왜 사이드 프로젝트 못 끝내?" → project-graveyard 발동

### 패턴 D — React/Next.js (18개)
```bash
cd generative_ui_agents/ai-dashboard-canvas-agent
npm install          # postinstall이 Python 에이전트까지 자동 셋업
cp .env.example .env
npm run dev          # UI(Next.js) + agent(Python) 동시 실행 → localhost:3000
```
요구사항: Node 18+ (Next 15.3.2 / React 19) + Python 3.10+

### 키 설정 3가지
```
① .env 파일 (가장 많음)            cp .env.example .env
② Streamlit 사이드바 직접 입력      코드에 하드코딩 없음 (보안 양호)
③ 환경변수                        export OPENAI_API_KEY=sk-xxxx
```

### 자주 터지는 에러
| 에러 | 원인 | 해결 |
|---|---|---|
| `ModuleNotFoundError` | 가상환경 미활성 | 프로젝트 폴더에서 venv 활성화 후 재설치 |
| `RateLimitError` / `insufficient_quota` | OpenAI 결제수단 없음 | 카드 등록 또는 Gemini/Ollama 버전 전환 |
| `streamlit: command not found` | 전역 설치됨 | venv 안에서 `pip install streamlit` |

## Q2. 플러그인? 스킬? MCP?

**정확한 답: 셋 다 아니고, 셋 다 일부 포함.** 저장소 전체는 **예제 모음집**입니다.

### 플러그인 — ❌ 아님
전체 1,887개 파일 검색 결과: `plugin.json` **0개**, `marketplace.json` **0개**.
Claude Code 플러그인 규격 파일이 하나도 없음 → "플러그인으로 설치" 불가.
(예외: `generative_ui_agents/ai-shadcn-component-generator/`에만 `.claude/settings.json` + `.mcp.json` — 그 프로젝트 내부 설정)

### 스킬 — ✅ 7개가 진짜 스킬
`SKILL.md` 보유 폴더 (agentskills.io 표준 준수):
```
agent_skills/advisor-orchestrator-worker/SKILL.md
agent_skills/commit-archaeologist/SKILL.md
agent_skills/dependency-doctor/SKILL.md
agent_skills/first-reader/SKILL.md
agent_skills/project-graveyard/SKILL.md
agent_skills/scope-creep-detector/SKILL.md
agent_skills/thinking-out-loud/SKILL.md
```
나머지 2개(`self-improving-agent-skills`, `evals`)는 SKILL.md 없이 backend/frontend를 가진 **앱·테스트 도구**.
추가로 `generative_ui_agents/ai-mcp-app-builder/` 내부에 SKILL.md 3개 존재(그 프로젝트가 쓰는 내부 스킬).

### MCP — 🔶 클라이언트 7 + 서버 4
```
MCP 클라이언트 (서버를 소비) — mcp_ai_agents/ 전체 7개
  github_mcp_agent, browser_mcp_agent, notion_mcp_agent,
  ai_travel_planner_mcp_agent_team, multi_mcp_agent_router,
  multi_mcp_agent, openai_remote_mcp_bridge

MCP 서버 (직접 구현) — 4개
  generative_ui_agents/ai-mcp-app-builder/apps/threejs-server/server.ts
  generative_ui_agents/ai-mcp-app-builder/apps/mcp-use-server/index.ts
  generative_ui_agents/mcp-apps-generative-ui-showcase/mcp-server/server.ts
  starter_ai_agents/ai_x402_paying_agent/seller.py
```

| 질문 | 답 | 개수 |
|---|---|---|
| 플러그인인가? | ❌ 전혀 아님 | 0 |
| 스킬인가? | ⚠️ 일부 (`agent_skills/`) | 7 |
| MCP인가? | ⚠️ 일부 (클라이언트 7 + 서버 4) | 11 |
| **나머지는?** | ✅ 독립 실행 앱 | 171 |

> **한 문장: "스킬 7개와 MCP 예제 11개를 포함한, 독립 AI 앱 182개짜리 소스코드 모음집"**

## Q3. API 토큰이 필요한가

**대부분 필요. 하지만 22개는 완전 무료.**

### 무료 경로 3가지
1. **Gemini** — 81개 프로젝트. `aistudio.google.com`에서 카드 등록 없이 키 발급. ADK 크래시코스 28챕터 전체가 Gemini 3 Flash 기준
2. **Ollama 로컬** — 13개 프로젝트. 비용 0원 / 키 0개
3. **Agent Skills** — 9개. 키 불필요, 네트워크 미사용
   `project-graveyard/SKILL.md` 원문: *"Everything runs locally. No API, no network, nothing leaves the machine."*
   `agent_skills/README.md`: *"Local and private by default. No network calls unless declared. Nothing leaves your machine."*

### 비용 절감 도구 (저장소 내장) ⭐
```
advanced_llm_apps/llm_optimization_tools/
├── toonify_token_optimization/     30~60% 절감 (TOON 포맷)
└── headroom_context_optimization/  50~90% 절감
```

### 추천 조합
```
[학습·개인용] Gemini 무료키 1개 + Ollama → 월 0원으로 약 95개 프로젝트 커버
[상업 서비스] OpenAI $20 선충전 + Gemini 무료 + 최적화 도구 → 거의 전부 커버
```

## Q4. AI 에이전트 구축에 도움이 되나

**YES. 단, "복붙 소스"보다 "설계 교과서" 용도가 압도적으로 더 가치 있습니다.**

### 도움되는 지점
1. **에이전트 패턴 지형도** — OpenAI SDK 크래시코스 11챕터가 그대로 설계 커리큘럼. 특히 5(컨텍스트)·6(가드레일)·10(관측)은 자료가 희귀하고 실무 난관
2. **"안 되는 패턴"을 미리 안다**
   - `rag_failure_diagnostics_clinic` — RAG 오류 체계적 진단
   - `corrective_rag` — 검색 결과 자기채점 후 재시도
   - `agentic_typed_rag_pydanticai` — **근거 약하면 답변 거부** ⭐
   - `trust_gated_agent_team` / `multi_agent_trust_layer` — 해시체인 감사추적
   - `ai_agent_governance` — 거버넌스
3. **프레임워크 선택 판단** — 동일 기능을 Agno / ADK / OpenAI SDK / CrewAI / LangGraph / AG2 / PydanticAI로 각각 구현한 걸 비교 가능
4. **프로덕션 품질 레퍼런스** — `always_on_agents/always_on_hn_briefing_agent/`
   ```
   agent.py  scout.py  delivery.py  scheduler_api.py
   tests/unit/test_scout.py  tests/unit/test_scheduler_api.py  tests/eval/eval_config.yaml
   ```
   README 명시: *"Defaults to dry-run mode and skips delivery unless credentials are explicitly configured"* — 기본 안전 모드
5. **에이전트 평가(eval) 방법** — `agent_skills/evals/` + `.github/workflows/skill-evals.yml`
   ```yaml
   for t in agent_skills/evals/*/test_*.py; do python3 "$t"; done   # + strict lint
   ```

### 한계 (솔직하게)
| 한계 | 설명 |
|---|---|
| Streamlit은 프로토타입 전용 | 74개가 Streamlit. 멀티유저/인증/확장성 없음 → 실서비스는 FastAPI+React 재작성 |
| 인증·과금·멀티테넌시 없음 | 전부 직접 구현 필요 |
| 에러처리 얇음 | 재시도/타임아웃/폴백 부족한 프로젝트 다수 |
| 버전 핀 불안정 | `agno>=2.2.10` 등 열려 있어 몇 달 뒤 깨질 수 있음 |
| 품질 편차 | `always_on_agents`(테스트 有) ↔ 일부 starter 격차 큼 |

### 올바른 활용법
```
❌ 폴더 복사 → 이름만 바꿔 배포 → 터짐
✅ 1. 유사 프로젝트 3개 "읽기" (패턴 추출)
   2. 내 스택(FastAPI + React)으로 재구현
   3. 가드레일·관측(6·10챕터)을 처음부터 포함
   4. agent_skills/evals/ 방식으로 평가 자동화
```
> **코드 창고로 쓰면 60점, 설계 교과서 + 패턴 사전으로 쓰면 95점.**

## Q5. 수익화 아이디어 (요약 — 상세는 4장)
```
① 버티컬 SaaS      — 범용을 업종 전용으로 좁히기 (추천 1순위)
② 교육 콘텐츠      — README 287개 + 커리큘럼 28챕터가 이미 강의 구조
③ Agent Skills 유통 — 유료 스킬 시장이 지금 거의 비어 있음
④ 구축 대행·컨설팅  — 182개 포트폴리오로 영업, 재사용으로 원가 절감
⑤ 운영형 상품      — always_on 패턴의 "알아서 도는 구독 서비스"
```

## Q6. React나 PHP로 만들 수 있나

### React — ✅ YES, 이미 저장소에 18개 있음 ⭐
`generative_ui_agents/`가 정확히 React 구현체. 실측 스택:
```json
"next": "15.3.2",  "react": "^19.0.0",
"@copilotkit/react-core": "^1.56.3",     // 에이전트 ↔ React 브릿지
"@copilotkit/runtime": "^1.56.3",
"@ag-ui/client": "^0.0.53",              // AG-UI 프로토콜
"recharts": "^2.15.4",
"@radix-ui/*", "tailwind-merge", "zod"   // shadcn/ui
```
권장 아키텍처 (저장소가 실제로 쓰는 방식):
```
[React / Next.js 15] ←── CopilotKit / AG-UI ──→ [Python 에이전트]
   UI 렌더링                스트리밍 프로토콜          agno / ADK
```
근거 — `package.json`:
```json
"dev": "concurrently \"npm run dev:ui\" \"npm run dev:agent\""
```
→ **UI와 에이전트를 분리 운영하는 게 정석.**

복사할 출발점: `generative-ui-starter-project`(가장 깔끔), `ai-shadcn-component-generator`, `ai-dashboard-canvas-agent`, `ai-deep-research-agent`

### PHP — ⚠️ 직접 구현은 비현실적, 하이브리드는 완전 가능
| 항목 | 현실 |
|---|---|
| 저장소 내 PHP 코드 | **0개** |
| PHP용 Agno/ADK | 없음 |
| PHP LangChain | 비공식 포팅, 생산성 낮음 |
| PHP 벡터DB/임베딩 생태계 | 매우 빈약 |

**❌ 비추천**: PHP로 에이전트 로직 직접 구현 (Python 10줄 = PHP 200줄)

**✅ 강력 추천**: PHP = 프론트/업무로직, Python = 에이전트 엔진
```
┌──────────────────────────────┐
│ PHP (Laravel / 기존 레거시)     │
│ 로그인·회원·권한 / 결제·정산      │
│ 관리자 페이지 / 기존 MySQL        │
└────────┬─────────────────────┘
         │ HTTP(JSON) / SSE 스트리밍
         ↓
┌──────────────────────────────┐
│ Python FastAPI               │ ← 저장소 코드 그대로 재사용
│ agno 에이전트 / RAG / Qdrant   │   (fastapi 12 + uvicorn 12 = 이미 존재)
└──────────────────────────────┘
```
```php
// app/Services/AgentService.php
$response = Http::timeout(120)
    ->post(config('services.agent.url').'/analyze', [
        'query'   => $request->input('q'),
        'user_id' => auth()->id(),
    ]);
return $response->json();
```
장점: 기존 PHP 자산(회원·결제·관리자)을 버리지 않음 / Python 코드 거의 그대로 재사용 / 에이전트만 독립 스케일링 / 병렬 개발 가능

### 스택 선택 가이드
| 상황 | 추천 |
|---|---|
| 신규 + React 가능 | Next.js + CopilotKit + Python (저장소 18개 활용) |
| 기존 PHP/Laravel 보유 | **PHP + Python FastAPI 하이브리드** ⭐ |
| 빠른 MVP·검증 | Streamlit 그대로 (1~2일) |
| 사내 도구 | Streamlit 그대로 |
| 상용 B2C | React + FastAPI (Streamlit은 멀티유저 불가) |

## Q7. 유튜브 강의 영상 제작 가능성

**매우 적합. 콘텐츠 측면에서 거의 "이미 만들어진 커리큘럼".**

### 유리한 조건
1. **번호순 커리큘럼 존재** — ADK 9 + OpenAI SDK 11 = 20화 시리즈 목차 그대로
2. **README 287개 = 스크립트 초안** — Features/How It Works/Requirements/Installation 이미 작성됨
3. **결과물이 화면에 보임** — Streamlit 74개가 즉시 시각적 결과
   (집 사진→리모델링 렌더, 음성→보험청구+웹캠, 밈 자동생성, AI 체스 대결)
4. **썸네일 소재 준비됨** — `docs/gallery/` + jpg 78 / png 56
5. **라이선스 안전** — Apache-2.0, 영상 제작·수익화 합법 (크레딧 명시 필수)
6. **한국어 콘텐츠 공백** — Agno, Google ADK, CopilotKit/AG-UI, Agent Skills 한국어 자료 거의 없음 → 선점 가능

### 리스크와 대응
| 리스크 | 대응 |
|---|---|
| 코드가 계속 바뀜 | 영상에 **커밋 해시 고정** + 설명란 명시 (`4f952d3`) |
| 저장소 소개 영상은 조회수 한계 | "소개"가 아니라 **"이걸로 OO 만들기"** 문제해결형 |
| API 키 화면 노출 사고 | 더미 키 + 블러 처리, 녹화 후 키 폐기 |
| 설치 과정이 지루함 | 설치는 1화에 몰아넣고 2화부터 스킵 |
| 의료·금융 예제 책임 | "데모용, 실제 진단/투자 판단 금지" 고지 자막 |
| 크레딧 누락 | 설명란에 원본 `Shubhamsaboo/awesome-llm-apps` + Apache-2.0 + LICENSE 링크 |

### 추천 시리즈 3안

**[A안] AI 에이전트 입문 10부작 — 초보 타깃, 조회수형**
```
1화  에이전트란? + 환경설정(Python/venv/키 발급)
2화  10분만에 첫 에이전트 (ai_travel_agent)
3화  내 엑셀에 질문하기 (ai_data_analysis_agent)
4화  무료로! Ollama 로컬 AI (local_rag_agent)        🔥 "0원" 후킹
5화  내 PDF로 챗봇 (autonomous_rag)
6화  AI 3명이 팀으로 (ai_finance_agent_team) — "20줄의 마법"
7화  AI가 브라우저 직접 조작 (browser_mcp_agent)
8화  목소리로 말하는 AI (voice_rag_openaisdk)
9화  Claude Code에 초능력 심기 (agent_skills)        ⭐ 차별화
10화 React로 진짜 제품 (generative-ui-starter-project)
```

**[B안] Agent Skills 완전정복 — 니치 선점형, 타이밍 최적** ⭐
```
1화 Agent Skills가 뭐고 왜 2026년의 핵심인가
2화 project-graveyard — 내 죽은 프로젝트 부검 (후킹 강력)
3화 SKILL.md 해부 — 좋은 스킬 vs 텍스트 덤프
4화 내 스킬 직접 만들기 (스크립트 + references 구조)
5화 CI로 스킬 자동 평가 (evals + GitHub Actions)
6화 스킬 배포하고 유료화하기
```
→ 한국어 자료 사실상 0개. 검색 선점 가능성 최고.

**[C안] RAG 마스터클래스 8부작 — 실무자 타깃, 전환율 높음**
```
1화 RAG 기초 (rag_chain)              5화 멀티모달 RAG (multimodal_agentic_rag)
2화 자율 RAG (autonomous_rag)          6화 지식그래프+출처검증 (knowledge_graph_rag_citations)
3화 스스로 고치는 RAG (corrective_rag) ⭐ 7화 DB 라우팅 (rag_database_routing)
4화 하이브리드 검색 (hybrid_search_rag) 8화 내 RAG가 왜 틀리나 — 진단 클리닉 ⭐
```

### 제작 실무 팁
```
✅ 1편 10~15분 (튜토리얼 최적)
✅ 영상 0~15초에 "완성 화면"부터 (이탈 방지)
✅ 설명란에 GitHub 링크 + 커밋 해시 + 타임스탬프
✅ 코드는 복붙 말고 "핵심 5줄만" 타이핑하며 설명
✅ "무료", "API 키 없이", "로컬에서" → 한국 시청자 반응 최상
✅ 시리즈 종료 후 → 유료 강의/템플릿 판매로 연결
```

---

# 4. 수익화 아이디어 상세

## 법적 기반
```
Apache-2.0
├─ ✅ 상업적 사용 / 수정 / 배포·판매 / 비공개(클로즈드) 배포  ← GPL과 결정적 차이
├─ ✅ 특허 라이선스 포함                                  ← MIT보다 기업 납품에 안전
├─ ⚠️ 의무 1: LICENSE 사본 유지
├─ ⚠️ 의무 2: 변경 사실 고지 (NOTICE 파일)
└─ ⚠️ 의무 3: 원저작자 저작권 표시 유지
```
README 원문: **"Fork it, ship it, sell it."**

🚨 **각 프로젝트의 하위 의존성 라이선스는 별개입니다.** 상용 납품 전 `pip-licenses` 등으로 전수 검사하세요.

## 아이디어 1. 버티컬 SaaS — 추천 1순위

### 핵심 전략: "범용을 좁혀라"
```
❌ 안 팔림: "AI 법률 에이전트"             ← ChatGPT로 되는데 왜 돈 내?
✅ 팔림:   "건설업 하도급계약 독소조항 검출기"  ← 대체재 없음
```
범용 AI는 무료 경쟁자가 있지만, 업종 특화는 **도메인 지식 + 데이터 + 워크플로우**가 들어가 복제가 어렵습니다.

### 변환 예시
| 저장소 원본 | 버티컬 전환 | 타깃 | 월 과금(예상) |
|---|---|---|---|
| `ai_legal_agent_team` | 건설 하도급 계약 리스크 검출 | 중소 건설사 | 15~50만 |
| `ai_recruitment_agent_team` | 개발자 이력서 1차 스크리닝 | 스타트업 HR | 10~30만 |
| `resume_job_matcher` | 반대 방향: 구직자용 JD 적합도 진단 | 개인 B2C | 월 9,900 / 건당 4,900 |
| `ai_fraud_investigation_agent` | 거래처 신용·실체 검증 | 무역·도매 | 20~60만 |
| `ai_customer_support_agent` | 쇼핑몰 CS 자동응답 (카페24/스마트스토어) | 이커머스 | 5~20만 |
| `earnings_call_analyst_agent` | IR 자료 요약 + 경쟁사 비교 | 증권·IR팀 | 50~200만 |

### 가장 유망: `always_on_agents` 패턴 ⭐
```
일회성 도구:  쓸 일 있을 때만 접속 → 해지율 높음 ("안 썼는데 왜 돈 내?")
always-on:   매일 아침 결과물 자동 도착 → 해지율 낮음 (안 써도 가치 체감)
```
| 변형 상품 | 내용 | 타깃 |
|---|---|---|
| 경쟁사 레이더 | 매일 아침 경쟁사 신제품·채용·가격변동 브리핑 | 마케팅팀 |
| **입찰 공고 알림** | 나라장터 신규 공고 중 내 업종 적합 건만 선별+요약 | 중소기업 ⭐ |
| 규제 변동 감시 | 식약처·금융위 고시 변경 → 사업 영향도 분석 | 규제산업 |
| 릴리즈 레이더 | 우리 스택 의존성 브레이킹체인지 사전 경고 | 개발팀 |

**인프라가 이미 구현돼 있음**: `scheduler_api.py`(FastAPI + Cloud Scheduler + Pub/Sub), `delivery.py`(Gmail/Slack/웹훅). 스케줄링·전송을 새로 만들 필요 없음.

### 실행 로드맵 (12주)
```
1~2주   타깃 선정 + 잠재고객 10명 인터뷰 (코드 작성 전!) → "돈 내고 쓰실 건가요?"
3~4주   Streamlit MVP (저장소 코드 거의 그대로) → 2~3명 무료 사용 + 피드백
5~8주   React/FastAPI 재구현 + 인증·결제·멀티테넌시 (또는 PHP 하이브리드)
9~10주  가드레일 + 관측 추가 (크래시코스 6·10챕터) — B2B는 이게 없으면 계약 불가
11~12주 베타 유료 3~5팀 → 가격 검증
```

### 가격 책정
```
원가 (사용자 1명/월): LLM API $3~15 + 인프라 $2~5 = $5~20
판매가: 원가 × 5~10배 = 월 5만~30만원   ← SaaS 표준 마진
```
💡 `llm_optimization_tools/`의 Toonify(30~60%) + Headroom(50~90%) 적용 시 **원가 절감이 마진으로 직결**. 저장소에서 가장 간과되는 자산.

## 아이디어 2. 교육 콘텐츠 — 가장 빨리 현금화
```
자산 현황
├─ README 287개              → 대본 초안
├─ 번호순 커리큘럼 28챕터       → 강의 목차 (기획 불필요)
├─ 돌아가는 코드 182개         → 실습 자료 (제작 불필요)
├─ 이미지 134장               → 썸네일 소재
└─ 한국어 자료 공백            → 수요 有, 공급 無
```

### 수익 5단 깔때기
```
[무료]  유튜브 시리즈                    → 모객
   ↓ 전환율 2~5%
[₩]    전자책 / Notion 가이드   2만~5만    → 가장 쉬운 첫 수익
[₩₩]   온라인 강의             15만~40만
[₩₩₩]  라이브 부트캠프(4주)     50만~150만
[₩₩₩₩] 기업 사내교육·워크숍(1일) 300만~800만  ← 단가 최고
```

### 차별화 앵글 (이게 핵심)
| 흔한 강의 | 차별화 |
|---|---|
| "GPT API 쓰기" (포화) | **"Agent Skills 완전정복"** — 한국어 자료 0개 ⭐ |
| "LangChain 입문" (포화) | **"Agno vs ADK vs OpenAI SDK 실전 비교"** — 구현체가 다 있음 |
| "RAG 만들기" (포화) | **"내 RAG가 왜 틀리는지 진단"** — 실무자 지불의사 높음 ⭐ |
| "AI 앱 배포" | **"에이전트 가드레일 + 관측"** — 자료 희귀 |
| - | **"API 비용 90% 줄이기"** — 제목만으로 클릭 ⭐ |

### 주의
- 저장소 코드 **그대로 유료 판매**는 법적으로 가능하나 평판 리스크 → **내 해설·재구성·실습데이터가 상품**이어야 함
- 설명란·강의자료에 원저작자 + Apache-2.0 + 원본 링크 **반드시** 명시
- 영상에 기준 커밋 해시 고정

## 아이디어 3. Agent Skills 유통 — 시장 공백, 선점 가능 ⭐
```
2023  ChatGPT 플러그인 → 사실상 소멸
2024  GPTs 스토어      → 수익화 실패
2025  MCP 서버         → 급성장, 개발 난도 높음
2026  Agent Skills     → 폴더 하나로 끝. 진입장벽 낮고 유료 시장 거의 비어 있음 ⭐
```
`agent_skills/README.md`의 시장 진단:
> *"Most 'skills' on registries are text-only prompt dumps: advice the model already knows, wrapped in frontmatter."*
→ **대부분이 쓰레기다 = 제대로 만들면 눈에 띈다.**

### 저장소의 품질 기준 = 내 상품의 차별화 기준
```
1. Real scripts          코드로 실행 (토큰 생성이 아니라)
2. Researched references 출처 있는 참고자료, 온디맨드 로드
3. Evidence over vibes   모든 주장이 검증 가능
4. Local and private     네트워크 미사용   ← 기업 판매 시 결정적 ⭐
5. Tested before shipped 실제 입력으로 테스트
```
④가 보안팀 통과의 핵심 조건입니다.

### 수익 모델
| 모델 | 방식 | 가격 감각 |
|---|---|---|
| 유료 스킬 팩 | 직군별 스킬 5~10개 묶음 | 3만~10만 (1회) |
| 팀 라이선스 | 사내 `.agents/skills/` 배포 + 업데이트 | 월 10만~50만 |
| **스킬 구축 대행** | 고객사 내부 규칙·컨벤션을 스킬화 | 건당 300만~1,000만 ⭐ |
| 스킬 + 교육 번들 | 스킬 + 교육 + 커스터마이징 | 500만~ |

### 한국 시장 특화 스킬 아이디어
```
① 한국어 코드리뷰 스킬 (국내 컨벤션/주석 스타일)
② 공공SI 산출물 생성기 (요구사항정의서/테스트시나리오) ⭐ 수요 큼
③ 개인정보보호법 점검 스킬 (코드 내 PII 처리 위반 탐지) ⭐
④ 레거시 PHP→Laravel 마이그레이션 스킬 (ai_codebase_migration_agent 참고)
⑤ 전자정부 프레임워크 규약 검사기
⑥ 국내 결제/PG 연동 체크리스트 스킬
```
②③⑤는 **외국 경쟁자가 만들 수 없는** 영역 = 진짜 moat.

### 신뢰 확보 장치 (그대로 복사)
```
.github/workflows/skill-evals.yml
├─ 모든 스킬 결정론적 eval 자동 실행
└─ strict lint
→ "우리 스킬은 CI 테스트를 통과합니다" = 유료 판매의 근거
```

## 아이디어 4. 구축 대행·컨설팅 — 가장 안정적, 즉시 매출
```
일반 외주사:  제안 → "유사 사례?" → 없음 → 수주 실패 → 0부터 6주 개발 → 마진 낮음
저장소 보유:  제안 → 유사 데모 즉시 시연 ⭐ → 수주 → 패턴 재사용 2주 → 마진 높음
```

| 서비스 | 기간 | 가격 감각 | 저장소 활용 |
|---|---|---|---|
| AI 도입 진단 워크숍 | 1~2일 | 300만~800만 | 182개 중 적합 후보 선별 + 데모 |
| PoC 구축 | 2~4주 | 800만~2,500만 | Streamlit 템플릿 그대로 |
| 본 개발 | 2~4개월 | 5,000만~2억 | React+FastAPI 재구현 |
| 운영·개선 리테이너 | 월 | 월 300만~1,000만 | 관측(10챕터) 기반 ⭐ |
| 사내 AI 교육 | 1~3일 | 500만~1,500만 | 크래시코스 28챕터 |

### 수주 확률을 높이는 무기 3개
**① 진단 클리닉으로 상담 진입** — `rag_failure_diagnostics_clinic`
> "지금 쓰시는 사내 챗봇이 왜 자꾸 틀린 답을 하는지 진단해드립니다"
→ 영업 멘트가 아닌 구체적 문제 해결 제안 → 미팅 성사율 높음. 진단하면 거의 항상 문제가 나옴 → 본 계약 연결

**② 신뢰 레이어로 대기업·금융 공략** — `trust_gated_agent_team`, `multi_agent_trust_layer`, `ai_agent_governance`
> 금융·의료·공공의 AI 도입 1순위 장벽이 "감사 추적 불가". 이 레퍼런스 보유 = 압도적 차별화 ⭐

**③ 비용 최적화로 기존 AI 사용처 공략** — `llm_optimization_tools`
> "월 OpenAI 비용 50~90% 줄여드리고 **절감액의 30%만** 받겠습니다"
→ 성과 기반(Gain-share) 과금이라 거절 명분이 거의 없음

## 아이디어 5. B2C 틈새 — 소자본·빠른 실험
| 원본 | 상품 | 과금 |
|---|---|---|
| `ai_blog_to_podcast_agent` | 블로그/뉴스레터 → 팟캐스트 | 건당 2,000 / 월 9,900 |
| `ai_audio_tour_agent` | 지역 맞춤 오디오 가이드 | 코스당 3,000~9,000 |
| `resume_job_matcher` | 이력서-공고 적합도 진단 + 개선안 | 건당 4,900 |
| `ai_health_fitness_agent` | 개인 맞춤 식단·운동 플랜 | 월 9,900 |
| `chat_with_youtube_videos` | 영상 → 요약노트·퀴즈 | 월 4,900 |
| `multimodal_video_moment_finder` | 영상 장면 검색 (편집자용) | 월 19,900 |
| `ai_meme_generator_agent_browseruse` | 밈 자동 생성 (SNS 운영자) | 월 9,900 |

```
✅ 장점: 영업 불필요, 빠른 검증, 초기 비용 적음
⚠️ 단점: CAC > LTV 되기 쉬움. 마케팅 역량이 제품보다 중요. 해지율 높음
   → 일회성 도구보다 "매일 자동 도착" 구조(always_on 패턴)가 유리
```

## 종합 추천 — 상황별 1순위
| 내 상황 | 추천 | 이유 |
|---|---|---|
| 직장인, 사이드 시작 | 교육 콘텐츠 (유튜브→전자책) | 자본 0, 저장소가 90% 완성 |
| **React 개발 가능** ⭐ | 버티컬 SaaS | `generative_ui_agents/` 18개 활용 |
| 기존 PHP 서비스 보유 | 기존 서비스에 AI 모듈 추가 | 고객·결제 이미 있음 → 최단 매출 |
| B2B 네트워크 있음 | 구축 대행 + 리테이너 | 즉시 매출, 안정적 |
| 기술력 높고 선점 희망 | Agent Skills 유통 | 시장 공백, 2026 타이밍 |
| 자본 적고 빠른 검증 | B2C 틈새 1개 | 1~2주 출시 |

### 가장 승률 높은 조합
```
[1단계] 유튜브 "Agent Skills 완전정복" (0~3개월)
        → 비용 0원, 한국어 공백 선점, 신뢰 구축
   ↓
[2단계] 시청자 B2B 문의 → 구축 대행 수주 (3~6개월)
        → 즉시 현금흐름. 포트폴리오 182개로 수주율 ↑
   ↓
[3단계] 대행 중 반복되는 요구 1개 발견 → 버티컬 SaaS 제품화 (6~12개월)
        → 실제 고객이 돈 낸 문제라 PMF 검증 완료 상태
   ↓
[4단계] 한국 특화 Agent Skills 유료 패키지 (병행)
```
**논리**: 교육으로 **신뢰** → 대행으로 **현금 + 진짜 수요 발견** → SaaS로 **확장**.
처음부터 SaaS를 만들면 "아무도 원하지 않는 걸 만들" 확률이 가장 높습니다.

## 수익화 전 필수 체크리스트
```
□ Apache-2.0 LICENSE 사본 포함
□ NOTICE 파일에 원저작자 + 변경 사실 명시
□ 하위 의존성 라이선스 전수 검사 (pip-licenses)
□ 의료/금융/법률 도메인 → 면책 고지 + 전문가 검수 필수
□ 개인정보 처리 → 개인정보보호법 검토 (국외이전 이슈: OpenAI API)
□ 가드레일 적용 (크래시코스 6챕터)  ← 환각 사고 = 계약 해지
□ 관측·로깅 적용 (크래시코스 10챕터) ← 없으면 운영 불가
□ 원가 최적화 적용 (llm_optimization_tools) ← 마진 직결
```

---

# 부록 A. 빠른 참조 — 바로 쓸 수 있는 것

## 오늘 당장 (0원, 10초)
```bash
npx skills add https://github.com/Shubhamsaboo/awesome-llm-apps/tree/main/agent_skills/project-graveyard
npx skills add https://github.com/Shubhamsaboo/awesome-llm-apps/tree/main/agent_skills/dependency-doctor
npx skills add https://github.com/Shubhamsaboo/awesome-llm-apps/tree/main/agent_skills/scope-creep-detector
```

## 0원으로 쓸 수 있는 22개
```
Agent Skills 9개          전부 로컬, 네트워크 미사용
Ollama 로컬 13개          키 0개, 비용 0원
+ Gemini 무료키 사용 시    약 95개 프로젝트까지 확장
```

## 목적별 시작점
| 하고 싶은 것 | 가야 할 폴더 |
|---|---|
| AI 앱 처음 만들어봄 | `starter_ai_agents/` |
| 내 문서로 챗봇 | `rag_tutorials/local_rag_agent` (무료) |
| Claude Code 강화 | `agent_skills/` |
| React로 AI UI | `generative_ui_agents/generative-ui-starter-project` |
| 외부 서비스 연결 | `mcp_ai_agents/` |
| 기초부터 순서대로 | `ai_agent_framework_crash_course/` |
| 24시간 자동 실행 | `always_on_agents/` |
| API 비용 절감 | `advanced_llm_apps/llm_optimization_tools/` |
| 에이전트 평가 자동화 | `agent_skills/evals/` + `.github/workflows/skill-evals.yml` |

---

# 부록 B. 조사 방법 (재현 가능)

이 문서의 수치는 아래 명령으로 재현할 수 있습니다.

```bash
# 전체 파일 수 / 타입별
git ls-files | wc -l
git ls-files | sed 's/.*\.//' | sort | uniq -c | sort -rn | head -20

# 독립 프로젝트 수
git ls-files | grep -E '(requirements\.txt|package\.json)$' | xargs -n1 dirname | sort -u | wc -l

# 의존성 빈도
cat $(git ls-files | grep 'requirements.txt$') | sed 's/[>=<~!].*//' | sed 's/\[.*//' \
  | tr -d ' \r' | grep -v '^$' | grep -v '^#' | sort | uniq -c | sort -rn | head -40

# API 키 등장 빈도
grep -rhoE '[A-Z][A-Z0-9_]*(API_KEY|_TOKEN|_KEY|_SECRET)' \
  --include=*.py --include=*.ts --include=*.tsx --include=*.example . \
  | sort | uniq -c | sort -rn | head -30

# 진짜 스킬 목록
git ls-files | grep 'SKILL.md'

# 플러그인 규격 여부 (결과 0개 = 플러그인 아님)
git ls-files | grep -iE 'plugin\.json|marketplace'

# MCP 서버 구현체
grep -rlE 'FastMCP|mcp\.server|@mcp\.tool' --include=*.py --include=*.ts .
```

---

*작성: Claude Code 세션 대화 정리 | 기준 커밋 `4f952d3` | 2026-10-07*
*원본 저장소: https://github.com/Shubhamsaboo/awesome-llm-apps (Apache-2.0)*
