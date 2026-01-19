**Scripted Pipeline – Top-Level Blocks**

```mermaid
flowchart TB
    A["Scripted Pipeline"] --> B["node { }"]

    subgraph "Top-Level (Scripted)"
        direction TB
        B --> AG["node / agent"]
        B --> ST["stage"]
        B --> ENV["env"]
        B --> TOOLS["tool"]
        B --> OPT["options (wrappers)"]
        B --> PARAM["params"]
        B --> TRIG["triggers (job config)"]
        B --> LIB["shared libraries"]
        B --> POST["post (try/catch/finally)"]
    end
```

**Agent / Node**

```mermaid
flowchart TB
A["Agent / Node"] --> B["node { }"]

subgraph "Agent Types"
direction TB
B --> N1["node('linux')"]
B --> N2["node('docker')"]
B --> N3["node('k8s')"]
B --> N4["docker.image('maven').inside { }"]
B --> N5["podTemplate { node(POD_LABEL) { } }"]
end
```

**Stages**

```mermaid
flowchart TB
A["Stages"] --> B["stage('Build') { }"]

subgraph "Stage Capabilities"
direction TB
B --> S1["sh / bat"]
B --> S2["withEnv"]
B --> S3["withCredentials"]
B --> S4["retry / timeout"]
B --> S5["parallel { }"]
B --> S6["custom loops (matrix style)"]
end
```

**Environment**

```mermaid
flowchart TB
A["Environment"] --> B["env"]

subgraph "Env Variables"
direction TB
B --> E1["env.APP = 'demo'"]
B --> E2["env.JAVA_HOME = tool 'jdk17'"]
B --> E3["env.DB_PASS = credentials('db-pass')"]
end
```

**Tools**

```mermaid
flowchart TB
A["Tools"] --> B["tool()"]

subgraph "Installed Tools"
direction TB
B --> T1["maven3"]
B --> T2["jdk17"]
B --> T3["node18"]
end
```

**Options / Wrappers**

```mermaid
flowchart TB
A["Options"] --> B["wrappers"]

subgraph "Build Wrappers"
direction TB
B --> O1["timeout(30)"]
B --> O2["timestamps"]
B --> O3["ansiColor('xterm')"]
B --> O4["retry(3)"]
B --> O5["lock('resource')"]
end
```

**Parameters

```mermaid
flowchart TB
A["Parameters"] --> B["params"]

subgraph "Job Parameters"
direction TB
B --> P1["params.ENV"]
B --> P2["params.DEPLOY"]
B --> P3["params.VERSION"]
end
```

**Triggers**

```mermaid
flowchart TB
A["Triggers"] --> B["Job Configuration"]

subgraph "Trigger Types"
direction TB
B --> T1["cron"]
B --> T2["pollSCM"]
B --> T3["webhook"]
B --> T4["upstream"]
end
```

**Shared Libraries**

```mermaid
flowchart TB
A["Shared Libraries"] --> B["@Library('shared-lib')"]

subgraph "Library Functions"
direction TB
B --> L1["build()"]
B --> L2["test()"]
B --> L3["deploy()"]
end
```

**Post / Error Handling**

```mermaid
flowchart TB
A["Post Actions"] --> B["try / catch / finally"]

subgraph "Result Handling"
direction TB
B --> P1["success logic"]
B --> P2["failure logic"]
B --> P3["cleanup"]
B --> P4["notifications"]
end
```
