# 🧠 AiNn Project Flowchart  
*System Architecture Logic – Text-Based Representation*

---

## Conventions
- `=== START/END ===`: Major session boundaries  
- `[Process]`: Action steps  
- `<Decision>`: Conditional logic checkpoints  
- `-->`: Flow direction  
- `...>`: Planned or future integration  
- *Italicized Notes*: Comments on implementation or future roadmap

---

## 🔄 Flowchart
=== START: User Initiates Chat ===
    |
    v
[AI Chat Interface Receives Input]
    |
    v
<Does Memory Stack Contain Relevant Context?>
    Y: --> [AI Retrieves Context from Memory Stack]
    |         |
    |         v
    N: --> [AI Generates Response Without Context]
    |         |
    |         v
    |     [AI Delivers Response to User]
    |         |
    |         v
    |     [Update Memory Stack with New Data]
    |         | 
    |         v
    |     <Is Memory Stack Approaching Token Limit?>
    |         Y: --> [Summarize and Compress Memory Stack]
    |         |         | 
    |         |         v
    |         |     [Offload Excess Data to Backend]
    |         |         | 
    |         |         ...> Backend Data Management
    |         |         |
    |         |         v
    |         N: ------>|
    |                   v
    |               <User Continues Chat?>
    |                   Y: --> Back to [AI Chat Interface Receives Input]
    |                   N: --> === END: Chat Session Concludes ===
    v
=== END: Chat Session Concludes ===

---

## 🧠 Architecture Summary

This flowchart outlines the key logic of the **AiNn memory system**:

### 🔁 Real-Time Stack:
- Captures recent interactions for short-term recall
- Runs compression to optimize LLM token usage

### 🧠 Decision Points:
- **Context retrieval**: Determines whether to inject memory at runtime
- **Token limit check**: Triggers summarization + offloading if memory stack overloads

### 📦 Future-Ready Integration:
- Data offload to **Database backend** is marked as planned but not yet active
- Memory management handled with modular rules (via AiRS), anticipating external orchestration

---

## 📌 Status
This diagram reflects the **current working logic** of AiNn and informs both dev-side implementation and long-term architectural evolution.  
All compression, retrieval, and offloading protocols are protected under the **HFI Open+ License v1.4**
