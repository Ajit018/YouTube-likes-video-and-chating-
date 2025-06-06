<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Razz Ajit - Multi-Feature Platform</title>
    <style>
        :root {
            --primary-color: #FF5733;
            --secondary-color: #33A8FF;
            --dark-color: #333;
            --light-color: #f5f5f5;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--light-color);
        }
        
        .header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 1.5rem;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
            position: relative;
        }
        
        .profile {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            border: 3px solid white;
            margin: 0 auto 10px;
            background-color: #ddd;
            overflow: hidden;
        }
        
        .profile img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .login-info {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 0.8rem;
            background: rgba(0,0,0,0.3);
            padding: 5px 10px;
            border-radius: 20px;
        }
        
        .container {
            display: flex;
            flex-wrap: wrap;
            padding: 20px;
            gap: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .section {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            padding: 15px;
            flex: 1;
            min-width: 300px;
        }
        
        .section-title {
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
            margin-top: 0;
            color: var(--dark-color);
            display: flex;
            align-items: center;
        }
        
        .section-title i {
            margin-right: 10px;
            color: var(--primary-color);
        }
        
        /* YouTube Video Section */
        .video-container {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 aspect ratio */
            height: 0;
            overflow: hidden;
            margin-bottom: 15px;
            border-radius: 8px;
            background-color: #000;
        }
        
        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }
        
        .video-info {
            padding: 10px 0;
        }
        
        .video-title {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .video-stats {
            display: flex;
            justify-content: space-between;
            color: #666;
            font-size: 0.9rem;
        }
        
        /* WhatsApp Chat Section */
        .chat-container {
            height: 400px;
            overflow-y: auto;
            background-color: #e5ddd5;
            padding: 10px;
            border-radius: 8px;
            background-image: url('https://web.whatsapp.com/img/bg-chat-tile-light_a4be512e7195b6b733d9110b408f075d.png');
            background-repeat: repeat;
            display: flex;
            flex-direction: column;
        }
        
        .message {
            max-width: 70%;
            padding: 8px 12px;
            margin-bottom: 10px;
            border-radius: 8px;
            word-wrap: break-word;
            position: relative;
        }
        
        .received {
            background-color: white;
            align-self: flex-start;
            border-top-left-radius: 0;
        }
        
        .sent {
            background-color: #dcf8c6;
            align-self: flex-end;
            border-top-right-radius: 0;
        }
        
        .message-time {
            font-size: 0.7rem;
            color: #666;
            text-align: right;
            margin-top: 3px;
        }
        
        .chat-input-container {
            display: flex;
            margin-top: 10px;
            background-color: white;
            border-radius: 20px;
            padding: 5px 10px;
            align-items: center;
        }
        
        .chat-input {
            flex: 1;
            padding: 8px;
            border: none;
            outline: none;
            background: transparent;
        }
        
        .chat-send-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 50%;
            width: 35px;
            height: 35px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }
        
        /* Instagram Stories */
        .stories-container {
            display: flex;
            overflow-x: auto;
            gap: 15px;
            padding: 10px 0;
            scrollbar-width: none; /* Firefox */
        }
        
        .stories-container::-webkit-scrollbar {
            display: none; /* Chrome/Safari */
        }
        
        .story {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            padding: 3px;
            background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888);
            flex-shrink: 0;
            position: relative;
        }
        
        .story-viewed {
            background: #ccc;
        }
        
        .story-inner {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background-color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }
        
        .story img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .story-username {
            position: absolute;
            bottom: -20px;
            width: 100%;
            text-align: center;
            font-size: 0.7rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        
        .your-story {
            border: 2px dashed #999;
            background: none;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        
        .add-story {
            font-size: 1.5rem;
            color: #999;
        }
        
        /* AI Chat Section */
        .ai-chat-container {
            height: 400px;
            display: flex;
            flex-direction: column;
        }
        
        .ai-messages {
            flex: 1;
            overflow-y: auto;
            padding: 10px;
            background-color: #f9f9f9;
            border-radius: 8px;
            margin-bottom: 10px;
        }
        
        .ai-message {
            background-color: #e6f3ff;
            padding: 10px 15px;
            border-radius: 12px;
            margin-bottom: 10px;
            max-width: 80%;
            font-size: 0.9rem;
        }
        
        .user-message {
            background-color: var(--primary-color);
            color: white;
            margin-left: auto;
        }
        
        .ai-input-container {
            display: flex;
            background-color: white;
            border-radius: 20px;
            padding: 5px 10px;
            align-items: center;
        }
        
        .ai-input {
            flex: 1;
            padding: 8px;
            border: none;
            outline: none;
            background: transparent;
        }
        
        .ai-send-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 50%;
            width: 35px;
            height: 35px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                flex-direction: column;
            }
            
            .section {
                min-width: auto;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <div class="header">
        <div class="login-info">
            Logged in as: +91XXXXXX123
        </div>
        <div class="profile">
            <img src="https://via.placeholder.com/80" alt="Razz Ajit">
        </div>
        <h1>Razz Ajit</h1>
        <p>Content Creator | Multi-Platform Features</p>
    </div>
    
    <div class="container">
        <!-- YouTube Video Section -->
        <div class="section">
            <h2 class="section-title">
                <i class="fab fa-youtube"></i> YouTube Video
            </h2>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" allowfullscreen></iframe>
            </div>
            <div class="video-info">
                <div class="video-title">Razz Ajit - Latest Vlog | Travel Adventures</div>
                <div class="video-stats">
                    <span>1.2M views</span>
                    <span>25K likes</span>
                </div>
            </div>
        </div>
        
        <!-- WhatsApp Chat Section -->
        <div class="section">
            <h2 class="section-title">
                <i class="fab fa-whatsapp"></i> WhatsApp Chat
            </h2>
            <div class="chat-container">
                <div class="message received">
                    Hey Razz, loved your latest video!
                    <div class="message-time">10:15 AM</div>
                </div>
                <div class="message sent">
                    Thanks! Glad you enjoyed it 😊
                    <div class="message-time">10:17 AM</div>
                </div>
                <div class="message received">
                    When is the next upload coming?
                    <div class="message-time">10:18 AM</div>
                </div>
                <div class="message sent">
                    Planning for Friday. Shooting tomorrow!
                    <div class="message-time">10:20 AM</div>
                </div>
                <div class="message received">
                    Can't wait! Will share with friends 👍
                    <div class="message-time">10:21 AM</div>
                </div>
            </div>
            <div class="chat-input-container">
                <input type="text" class="chat-input" placeholder="Type a message...">
                <button class="chat-send-btn">
                    <i class="fas fa-paper-plane"></i>
                </button>
            </div>
        </div>
        
        <!-- Instagram Stories Section -->
        <div class="section">
            <h2 class="section-title">
                <i class="fab fa-instagram"></i> Instagram Stories
            </h2>
            <div class="stories-container">
                <div class="story your-story">
                    <div class="story-inner">
                        <div class="add-story">+</div>
                    </div>
                    <div class="story-username">Your Story</div>
                </div>
                <div class="story">
                    <div class="story-inner">
                        <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="Story 1">
                    </div>
                    <div class="story-username">travel_girl</div>
                </div>
                <div class="story">
                    <div class="story-inner">
                        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Story 2">
                    </div>
                    <div class="story-username">foodie_raj</div>
                </div>
                <div class="story story-viewed">
                    <div class="story-inner">
                        <img src="https://randomuser.me/api/portraits/women/68.jpg" alt="Story 3">
                    </div>
                    <div class="story-username">tech_reviews</div>
                </div>
                <div class="story">
                    <div class="story-inner">
                        <img src="https://randomuser.me/api/portraits/men/75.jpg" alt="Story 4">
                    </div>
                    <div class="story-username">fitness_guru</div>
                </div>
                <div class="story">
                    <div class="story-inner">
                        <img src="https://randomuser.me/api/portraits/women/90.jpg" alt="Story 5">
                    </div>
                    <div class="story-username">fashionista</div>
                </div>
            </div>
            <p style="text-align: center; margin-top: 30px; color: #666;">
                <i class="fas fa-arrow-up"></i> Swipe up to see more stories
            </p>
        </div>
        
        <!-- AI Chat Section -->
        <div class="section">
            <h2 class="section-title">
                <i class="fas fa-robot"></i> Razz AI Assistant
            </h2>
            <div class="ai-chat-container">
                <div class="ai-messages">
                    <div class="ai-message">
                        Hello Razz! I'm your AI assistant. How can I help you with your content creation today?
                    </div>
                    <div class="ai-message user-message">
                        What video ideas do you suggest for my channel?
                    </div>
                    <div class="ai-message">
                        Based on your audience, I suggest:<br>
                        1. "Day in my life as a creator" vlog<br>
                        2. Collaboration with travel_girl<br>
                        3. Q&A session with fans<br>
                        4. Behind-the-scenes of your shoot
                    </div>
                </div>
                <div class="ai-input-container">
                    <input type="text" class="ai-input" placeholder="Ask Razz AI anything...">
                    <button class="ai-send-btn">
                        <i class="fas fa-paper-plane"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>
    
    <script>
        // WhatsApp Chat Functionality
        const chatInput = document.querySelector('.chat-input');
        const chatSendBtn = document.querySelector('.chat-send-btn');
        const chatContainer = document.querySelector('.chat-container');
        
        chatSendBtn.addEventListener('click', sendMessage);
        chatInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') sendMessage();
        });
        
        function sendMessage() {
            const message = chatInput.value.trim();
            if (message) {
                const messageDiv = document.createElement('div');
                messageDiv.className = 'message sent';
                messageDiv.innerHTML = `
                    ${message}
                    <div class="message-time">${getCurrentTime()}</div>
                `;
                chatContainer.appendChild(messageDiv);
                chatInput.value = '';
                chatContainer.scrollTop = chatContainer.scrollHeight;
                
                // Simulate reply after 1 second
                setTimeout(() => {
                    const replies = [
                        "That's interesting!",
                        "I'll get back to you soon",
                        "Thanks for your message!",
                        "Let me check and reply",
                        "👍"
                    ];
                    const replyDiv = document.createElement('div');
                    replyDiv.className = 'message received';
                    replyDiv.innerHTML = `
                        ${replies[Math.floor(Math.random() * replies.length)]}
                        <div class="message-time">${getCurrentTime()}</div>
                    `;
                    chatContainer.appendChild(replyDiv);
                    chatContainer.scrollTop = chatContainer.scrollHeight;
                }, 1000);
            }
        }
        
        // AI Chat Functionality
        const aiInput = document.querySelector('.ai-input');
        const aiSendBtn = document.querySelector('.ai-send-btn');
        const aiMessages = document.querySelector('.ai-messages');
        
        aiSendBtn.addEventListener('click', sendAiMessage);
        aiInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') sendAiMessage();
        });
        
        function sendAiMessage() {
            const message = aiInput.value.trim();
            if (message) {
                const messageDiv = document.createElement('div');
                messageDiv.className = 'ai-message user-message';
                messageDiv.textContent = message;
                aiMessages.appendChild(messageDiv);
                aiInput.value = '';
                aiMessages.scrollTop = aiMessages.scrollHeight;
                
                // Simulate AI thinking
                const thinkingDiv = document.createElement('div');
                thinkingDiv.className = 'ai-message';
                thinkingDiv.textContent = '...';
                aiMessages.appendChild(thinkingDiv);
                aiMessages.scrollTop = aiMessages.scrollHeight;
                
                // Generate AI response after 1.5 seconds
                setTimeout(() => {
                    aiMessages.removeChild(thinkingDiv);
                    
                    const responses = [
                        "That's a great question! For your channel, I'd suggest focusing on more interactive content.",
                        "Based on your analytics, your audience engages most with travel content. Maybe plan a trip series?",
                        "Have you considered doing a live stream with your subscribers?",
                        "Your editing skills have improved a lot! Maybe make a tutorial video?",
                        "Let me analyze your recent performance and suggest some hashtags..."
                    ];
                    
                    const responseDiv = document.createElement('div');
                    responseDiv.className = 'ai-message';
                    responseDiv.textContent = responses[Math.floor(Math.random() * responses.length)];
                    aiMessages.appendChild(responseDiv);
                    aiMessages.scrollTop = aiMessages.scrollHeight;
                }, 1500);
            }
        }
        
        // Helper function to get current time
        function getCurrentTime() {
            const now = new Date();
            let hours = now.getHours();
            const minutes = now.getMinutes().toString().padStart(2, '0');
            const ampm = hours >= 12 ? 'PM' : 'AM';
            hours = hours % 12;
            hours = hours ? hours : 12; // the hour '0' should be '12'
            return `${hours}:${minutes} ${ampm}`;
        }
        
        // Make stories clickable
        document.querySelectorAll('.story:not(.your-story)').forEach(story => {
            story.addEventListener('click', function() {
                this.classList.add('story-viewed');
                alert(`Opening story from ${this.querySelector('.story-username').textContent}`);
            });
        });
        
        // Your story click
        document.querySelector('.your-story').addEventListener('click', function() {
            alert('Add to your story feature would open here');
        });
    </script>
</body>
</html>
