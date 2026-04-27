[Browser-Based Wizardry](https://dev.to/sakethkowtha/browser-based-wizardry-unleashing-llms-without-melting-your-cpu-1b3j)

[LlamaIndex.TS](https://github.com/run-llama/LlamaIndexTS/tree/main)


[DSPy for Typescript](https://github.com/ax-llm/ax)

[tsbro](https://github.com/stagas/tsbro)
TypeScript for the Browser. No tooling, no build step, simply works.


[pi-mono](https://github.com/badlogic/pi-mono/tree/main/packages/agent)

```
npm install @mariozechner/pi-agent-core
```

```
import { Agent } from "@mariozechner/pi-agent-core";
import { getModel } from "@mariozechner/pi-ai";

const agent = new Agent({
  initialState: {
    systemPrompt: "You are a helpful assistant.",
    model: getModel("anthropic", "claude-sonnet-4-20250514"),
  },
});

agent.subscribe((event) => {
  if (event.type === "message_update" && event.assistantMessageEvent.type === "text_delta") {
    // Stream just the new text chunk
    process.stdout.write(event.assistantMessageEvent.delta);
  }
});

await agent.prompt("Hello!");
```
