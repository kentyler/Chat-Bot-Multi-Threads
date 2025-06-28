# Multi-Thread Response Instructions

## Universal Instruction (All Platforms)

Copy and paste this into your AI system:

```
When responding to complex topics, organize your analysis into 2-4 distinct threads using this format:

**Thread 1: [Descriptive Name]**
[Your analysis from this perspective]

**Thread 2: [Descriptive Name]**
[Your analysis from this different perspective]

Continue this pattern as needed. Each thread should offer a genuinely different analytical angle, not variations of the same idea.

Users can interact with threads in several ways:
- Write normal prompts without markup (you decide which threads to advance)
- Target specific threads: "Thread 2: [their question]"
- Request new perspectives: "New thread: [topic]"
- Close threads: "Kill thread 3" or "Remove thread 2"

You can also spawn new threads or terminate threads naturally as the conversation evolves.
```

## Platform-Specific Instructions

### ChatGPT

1. Go to Settings → Personalization → Custom Instructions
2. In "How would you like ChatGPT to respond?" paste the universal instruction
3. Save and start a new conversation

### Claude

Simply paste the universal instruction at the beginning of a new conversation. Claude will maintain the threading approach throughout that conversation.

### Google Gemini

Include the universal instruction at the start of your conversation or in the system instructions if using the API.

### Local LLMs (Ollama, LM Studio, etc.)

Add the universal instruction to your system prompt configuration.

### API Integration

For programmatic use, include the instruction in your system message:

```python
system_message = """
When responding to complex topics, organize your analysis into 2-4 distinct threads...
[rest of universal instruction]
"""

messages = [
    {"role": "system", "content": system_message},
    {"role": "user", "content": "Should we expand internationally?"}
]
```

## Usage Examples

### Basic Interaction
```
You: What's our competitive position?

AI: **Thread 1: Market Share Analysis**
Current position shows 15% market share...

**Thread 2: Innovation Pipeline**
R&D investments suggest strong future position...

**Thread 3: Brand Perception**
Customer surveys indicate declining brand strength...
```

### Thread Targeting
```
You: Thread 2: Tell me more about the R&D investments

AI: **Thread 2: Innovation Pipeline (Expanded)**
Three major initiatives in development...
```

### Adding New Threads
```
You: New thread: What about regulatory risks?

AI: **Thread 4: Regulatory Landscape**
Upcoming legislation could impact operations...
```

### Removing Threads
```
You: Kill thread 1, market share isn't relevant right now

AI: [Thread 1 removed - continuing with remaining threads]
```

### All-Thread Commands
```
You: All threads: How does this impact our 5-year plan?

AI: **Thread 2: Innovation Pipeline**
5-year impact: R&D investments position us...

**Thread 3: Brand Perception**
5-year impact: Brand rehabilitation needed...

**Thread 4: Regulatory Landscape**
5-year impact: Compliance costs will increase...
```

## Best Practices

### Thread Management
- Start with 2-4 threads for most questions
- Let threads evolve naturally
- Kill threads that no longer add value
- Spawn new threads when new angles emerge

### Quality Indicators
Good threads:
- Represent genuinely different perspectives
- Could be simultaneously true
- Reveal different aspects of the situation
- Don't just restate the same point

Poor threads:
- Variations on the same theme
- Forced perspectives that don't fit
- Too many threads (cognitive overload)
- Artificial disagreement

### Natural Flow
- 80% of the time, just write normally
- Target specific threads when diving deep
- Use thread commands sparingly
- Let the AI manage thread lifecycle

## Troubleshooting

**Problem**: AI creates too many threads
**Solution**: Ask to consolidate to 2-3 most important perspectives

**Problem**: Threads seem too similar
**Solution**: Request "more distinct analytical angles"

**Problem**: AI forgets threading format
**Solution**: Remind with "Please use thread format" or restart conversation

**Problem**: Threads don't evolve
**Solution**: Actively engage with specific threads to encourage development