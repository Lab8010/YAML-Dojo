# 100問の問題バンク設計

現在は各分野・各難易度を動作確認できる9問を収録しています。問題データは安定ID、分野、難易度、出題形式、日英テキストを持つため、そのまま100問まで追加できます。

## 推奨配分

| 分野 | 初級 | 中級 | 上級 | 合計 |
|---|---:|---:|---:|---:|
| Kubernetes | 12 | 11 | 11 | 34 |
| OpenShift | 11 | 11 | 11 | 33 |
| Ansible Playbook | 11 | 11 | 11 | 33 |
| 合計 | 34 | 33 | 33 | 100 |

初級は2つのYAMLから正しい方を選ぶ形式、中級は欠けた値やブロックの補完、上級は要件からのYAML記述を基本にします。

## Kubernetes 34問

- Pod名、apiVersion、リスト、インデント、labels、selectors、ports
- Deployment、StatefulSet、DaemonSet、Job、CronJob
- ConfigMap、Secret、環境変数、Volume、PVC
- readiness/liveness/startup probe、requests/limits
- Namespace、ServiceAccount、Role/RoleBinding、NetworkPolicy
- affinity、tolerations、securityContext、PodDisruptionBudget

## OpenShift 33問

- Route、TLS termination、HTTP redirect、weighted backends
- ImageStream、ImageStreamTag、local lookup
- BuildConfig、Git source、S2I、Docker strategy、webhook
- Project、Template、parameters
- SecurityContextConstraints、OperatorGroup、Subscription
- MachineConfig、MachineConfigPool、OpenShift固有APIの識別

管理者権限が必要なSCC、Operator、MachineConfig問題には、対象ロールを明記します。DeploymentConfigは新規作成の中心にはせず、既存環境の読解・Deploymentへの移行問題として扱います。

## Ansible Playbook 33問

- plays、hosts、tasks、FQCN、インデント、boolean
- apt/dnf/package、service、copy、template、file、user
- variables、facts、Jinja2、loop、when、register、tags
- handlers、notify、block/rescue/always、assert
- serial、delegate_to、uriによるヘルスチェック
- Gitデプロイ、Vault変数、no_log、冪等性

## 次に相性がよい題材

優先度順では、次の分野がYAML学習との相性に優れています。

1. **Kustomize** — base/overlayとpatchを通して、Manifestの差分管理を学べる
2. **Tekton / Argo CD** — PipelineやGitOpsをYAMLで体験できる
3. **GitHub Actions** — 身近なCI/CD題材で、イベント・job・stepを学べる
4. **Helm values** — values.yamlの読解に向く。ただしテンプレート構文はYAMLとは別枠で扱う
5. **Docker Compose** — YAML初学者の入口に向く
6. **PrometheusRule** — アラート条件と運用設計を学べる

まず100問は3本柱に集中し、その後「GitOps道場」としてKustomize・Tekton・Argo CDを追加する構成がおすすめです。

## 品質管理

- 問題IDを公開後に変更しない（進捗データとの互換性を保つ）
- Kubernetes/OpenShiftの対象バージョン、Ansible Coreの対象バージョンを記録する
- 日英を同時レビューし、英訳で要件が増減しないようにする
- 上級問題は将来的にYAMLパーサーで構造を採点する
- 非推奨APIや権限の強いリソースには注記を付ける
