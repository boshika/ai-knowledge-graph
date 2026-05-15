Converts text to life-like speech. Mainly used in the output layer for voice-based applications.
**How to Use Polly in a GenAI Pipeline**

1. **Generation:** A foundation model (like Claude on Amazon Bedrock) generates a text response based on a user's query.
2. **Synthesis:** Your application sends this generated text to the Amazon Polly API.
3. **Output:** Polly converts the text into a high-quality audio stream (such as an MP3 file) that your application plays back to the user.

**Voice AI Pipeline Architecture**

- **Input Layer:** [[Amazon Transcribe]](Audio → Text).
- **Reasoning Layer:** [[Amazon Bedrock]] (Text → Generated Text).
- **Output Layer:** **Amazon Polly** (Text → Audio)

While **Amazon Transcribe** is a pre-processing service for voice input, **Amazon Polly** is a post-processing service for voice output