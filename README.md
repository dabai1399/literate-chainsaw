[社媒1.html](https://github.com/user-attachments/files/22587386/1.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SocialConnect - 连接你我他</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #1877f2;
            --secondary: #42b72a;
            --bg-color: #f0f2f5;
            --card-bg: #ffffff;
            --text-primary: #1c1e21;
            --text-secondary: #65676b;
            --border: #dddfe2;
            --shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-primary);
            line-height: 1.6;
        }

        .container {
            display: flex;
            min-height: 100vh;
        }

        /* 侧边栏样式 */
        .sidebar {
            width: 280px;
            background: var(--card-bg);
            box-shadow: var(--shadow);
            padding: 20px 0;
            position: fixed;
            height: 100vh;
            overflow-y: auto;
            z-index: 100;
        }

        .logo {
            display: flex;
            align-items: center;
            padding: 0 20px 20px;
            border-bottom: 1px solid var(--border);
            margin-bottom: 20px;
        }

        .logo i {
            color: var(--primary);
            font-size: 32px;
            margin-right: 10px;
        }

        .logo h1 {
            font-size: 24px;
            color: var(--text-primary);
        }

        .nav-links {
            list-style: none;
            padding: 0 15px;
        }

        .nav-links li {
            margin-bottom: 5px;
        }

        .nav-links a {
            display: flex;
            align-items: center;
            padding: 12px 15px;
            text-decoration: none;
            color: var(--text-primary);
            border-radius: 8px;
            transition: all 0.3s;
        }

        .nav-links a:hover, .nav-links a.active {
            background-color: #f0f2f5;
        }

        .nav-links i {
            margin-right: 12px;
            font-size: 20px;
            width: 24px;
            text-align: center;
        }

        /* 主内容区样式 */
        .main-content {
            flex: 1;
            margin-left: 280px;
            padding: 20px;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--card-bg);
            padding: 15px 20px;
            border-radius: 10px;
            box-shadow: var(--shadow);
            margin-bottom: 20px;
        }

        .search-bar {
            flex: 1;
            max-width: 500px;
            position: relative;
        }

        .search-bar input {
            width: 100%;
            padding: 12px 20px 12px 40px;
            border: 1px solid var(--border);
            border-radius: 20px;
            background: var(--bg-color);
            font-size: 14px;
        }

        .search-bar i {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-secondary);
        }

        .user-actions {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .user-profile {
            display: flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
        }

        .avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        /* 内容区域 */
        .content {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 20px;
        }

        /* 发帖区域 */
        .create-post {
            background: var(--card-bg);
            border-radius: 10px;
            padding: 15px;
            box-shadow: var(--shadow);
            margin-bottom: 20px;
        }

        .post-input {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 15px;
        }

        .post-input .avatar {
            width: 40px;
            height: 40px;
        }

        .post-input input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid var(--border);
            border-radius: 20px;
            background: var(--bg-color);
        }

        .post-actions {
            display: flex;
            justify-content: space-around;
            border-top: 1px solid var(--border);
            padding-top: 10px;
        }

        .post-action {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .post-action:hover {
            background: var(--bg-color);
        }

        /* 帖子样式 */
        .post {
            background: var(--card-bg);
            border-radius: 10px;
            padding: 15px;
            box-shadow: var(--shadow);
            margin-bottom: 20px;
        }

        .post-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 15px;
        }

        .post-user {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .post-user .avatar {
            width: 40px;
            height: 40px;
        }

        .user-info h3 {
            font-size: 16px;
            margin-bottom: 2px;
        }

        .user-info span {
            font-size: 13px;
            color: var(--text-secondary);
        }

        .post-content {
            margin-bottom: 15px;
        }

        .post-image {
            width: 100%;
            border-radius: 10px;
            margin-bottom: 15px;
            max-height: 400px;
            object-fit: cover;
        }

        .post-stats {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-top: 1px solid var(--border);
            border-bottom: 1px solid var(--border);
            margin-bottom: 10px;
            color: var(--text-secondary);
            font-size: 14px;
        }

        .post-actions-buttons {
            display: flex;
            justify-content: space-around;
        }

        .post-button {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s;
            flex: 1;
            justify-content: center;
        }

        .post-button:hover {
            background: var(--bg-color);
        }

        /* 右侧边栏 */
        .right-sidebar {
            background: var(--card-bg);
            border-radius: 10px;
            padding: 20px;
            box-shadow: var(--shadow);
            height: fit-content;
        }

        .sidebar-title {
            font-size: 18px;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border);
        }

        .friend-list {
            list-style: none;
        }

        .friend-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px 0;
            border-bottom: 1px solid var(--border);
        }

        .friend-item:last-child {
            border-bottom: none;
        }

        .friend-item .avatar {
            width: 40px;
            height: 40px;
        }

        /* 响应式设计 */
        @media (max-width: 1200px) {
            .content {
                grid-template-columns: 1fr;
            }
            
            .right-sidebar {
                display: none;
            }
        }

        @media (max-width: 768px) {
            .sidebar {
                width: 70px;
            }
            
            .sidebar .logo h1, .sidebar .nav-links span {
                display: none;
            }
            
            .main-content {
                margin-left: 70px;
            }
            
            .nav-links a {
                justify-content: center;
                padding: 15px;
            }
            
            .nav-links i {
                margin-right: 0;
            }
        }

        /* 模态框样式 */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: white;
            border-radius: 10px;
            width: 90%;
            max-width: 500px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--border);
            border-radius: 5px;
            font-size: 16px;
        }

        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 500;
            transition: all 0.3s;
        }

        .btn-primary {
            background: var(--primary);
            color: white;
        }

        .btn-primary:hover {
            background: #166fe5;
        }

        .btn-block {
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- 侧边栏 -->
        <div class="sidebar">
            <div class="logo">
                <i class="fas fa-users"></i>
                <h1>SocialConnect</h1>
            </div>
            <ul class="nav-links">
                <li><a href="#" class="active"><i class="fas fa-home"></i> <span>首页</span></a></li>
                <li><a href="#"><i class="fas fa-user-friends"></i> <span>好友</span></a></li>
                <li><a href="#"><i class="fas fa-users"></i> <span>群组</span></a></li>
                <li><a href="#"><i class="fas fa-store"></i> <span>商城</span></a></li>
                <li><a href="#"><i class="fas fa-video"></i> <span>视频</span></a></li>
                <li><a href="#"><i class="fas fa-calendar-alt"></i> <span>活动</span></a></li>
                <li><a href="#"><i class="fas fa-cog"></i> <span>设置</span></a></li>
            </ul>
        </div>

        <!-- 主内容区 -->
        <div class="main-content">
            <div class="header">
                <div class="search-bar">
                    <i class="fas fa-search"></i>
                    <input type="text" placeholder="搜索 SocialConnect">
                </div>
                <div class="user-actions">
                    <div class="user-profile" id="userProfile">
                        <div class="avatar">天</div>
                        <span>阿天</span>
                    </div>
                </div>
            </div>

            <div class="content">
                <div class="left-content">
                    <!-- 发帖区域 -->
                    <div class="create-post">
                        <div class="post-input">
                            <div class="avatar">天</div>
                            <input type="text" placeholder="阿天，今天有什么新鲜事？" id="postInput">
                        </div>
                        <div class="post-actions">
                            <div class="post-action" id="photoBtn">
                                <i class="fas fa-image" style="color: #45bd62;"></i>
                                <span>照片/视频</span>
                            </div>
                            <div class="post-action" id="feelingBtn">
                                <i class="fas fa-smile" style="color: #f7b928;"></i>
                                <span>感受/活动</span>
                            </div>
                        </div>
                    </div>

                    <!-- 帖子流 -->
                    <div class="posts">
                        <!-- 示例帖子 1 -->
                        <div class="post">
                            <div class="post-header">
                                <div class="post-user">
                                    <div class="avatar" style="background: #e44d26;">小</div>
                                    <div class="user-info">
                                        <h3>小明</h3>
                                        <span>2小时前 · <i class="fas fa-globe-asia"></i></span>
                                    </div>
                                </div>
                            </div>
                            <div class="post-content">
                                <p>刚刚完成了一个超酷的项目！使用了最新的前端技术栈，用户体验大幅提升！🚀</p>
                            </div>
                            <div class="post-stats">
                                <div class="likes">
                                    <i class="fas fa-thumbs-up"></i> 42
                                </div>
                                <div class="comments">
                                    15 条评论
                                </div>
                            </div>
                            <div class="post-actions-buttons">
                                <div class="post-button like-btn">
                                    <i class="far fa-thumbs-up"></i>
                                    <span>点赞</span>
                                </div>
                                <div class="post-button comment-btn">
                                    <i class="far fa-comment"></i>
                                    <span>评论</span>
                                </div>
                                <div class="post-button share-btn">
                                    <i class="far fa-share-square"></i>
                                    <span>分享</span>
                                </div>
                            </div>
                        </div>

                        <!-- 示例帖子 2 -->
                        <div class="post">
                            <div class="post-header">
                                <div class="post-user">
                                    <div class="avatar" style="background: #17a2b8;">小</div>
                                    <div class="user-info">
                                        <h3>小红</h3>
                                        <span>5小时前 · <i class="fas fa-globe-asia"></i></span>
                                    </div>
                                </div>
                            </div>
                            <div class="post-content">
                                <p>周末去爬山了，山顶的风景太美了！推荐大家也去试试～</p>
                                <img src="https://images.unsplash.com/photo-1506905925346-21bda4d32df4?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Mountain view" class="post-image">
                            </div>
                            <div class="post-stats">
                                <div class="likes">
                                    <i class="fas fa-thumbs-up"></i> 128
                                </div>
                                <div class="comments">
                                    36 条评论
                                </div>
                            </div>
                            <div class="post-actions-buttons">
                                <div class="post-button like-btn">
                                    <i class="far fa-thumbs-up"></i>
                                    <span>点赞</span>
                                </div>
                                <div class="post-button comment-btn">
                                    <i class="far fa-comment"></i>
                                    <span>评论</span>
                                </div>
                                <div class="post-button share-btn">
                                    <i class="far fa-share-square"></i>
                                    <span>分享</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- 右侧边栏 -->
                <div class="right-sidebar">
                    <h3 class="sidebar-title">好友动态</h3>
                    <ul class="friend-list">
                        <li class="friend-item">
                            <div class="avatar" style="background: #28a745;">李</div>
                            <div>
                                <h4>李华</h4>
                                <span>发布了新照片</span>
                            </div>
                        </li>
                        <li class="friend-item">
                            <div class="avatar" style="background: #dc3545;">王</div>
                            <div>
                                <h4>王芳</h4>
                                <span>更新了状态</span>
                            </div>
                        </li>
                        <li class="friend-item">
                            <div class="avatar" style="background: #ffc107;">张</div>
                            <div>
                                <h4>张三</h4>
                                <span>加入了新群组</span>
                            </div>
                        </li>
                        <li class="friend-item">
                            <div class="avatar" style="background: #6f42c1;">赵</div>
                            <div>
                                <h4>赵四</h4>
                                <span>分享了链接</span>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <!-- 登录模态框 -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>登录 SocialConnect</h2>
                <button class="close-modal">&times;</button>
            </div>
            <form id="loginForm">
                <div class="form-group">
                    <label for="email">邮箱</label>
                    <input type="email" id="email" required>
                </div>
                <div class="form-group">
                    <label for="password">密码</label>
                    <input type="password" id="password" required>
                </div>
                <button type="submit" class="btn btn-primary btn-block">登录</button>
            </form>
            <p style="text-align: center; margin-top: 15px;">
                <a href="#" id="showRegister">创建新账号</a>
            </p>
        </div>
    </div>

    <!-- 注册模态框 -->
    <div class="modal" id="registerModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>注册 SocialConnect</h2>
                <button class="close-modal">&times;</button>
            </div>
            <form id="registerForm">
                <div class="form-group">
                    <label for="fullName">全名</label>
                    <input type="text" id="fullName" required>
                </div>
                <div class="form-group">
                    <label for="regEmail">邮箱</label>
                    <input type="email" id="regEmail" required>
                </div>
                <div class="form-group">
                    <label for="regPassword">密码</label>
                    <input type="password" id="regPassword" required>
                </div>
                <div class="form-group">
                    <label for="birthday">生日</label>
                    <input type="date" id="birthday" required>
                </div>
                <button type="submit" class="btn btn-primary btn-block">注册</button>
            </form>
            <p style="text-align: center; margin-top: 15px;">
                <a href="#" id="showLogin">已有账号？登录</a>
            </p>
        </div>
    </div>

    <script>
        // 模拟数据
        const users = [
            { id: 1, name: "阿天", avatar: "天", color: "#1877f2" },
            { id: 2, name: "小明", avatar: "小", color: "#e44d26" },
            { id: 3, name: "小红", avatar: "小", color: "#17a2b8" }
        ];

        const posts = [
            {
                id: 1,
                userId: 2,
                content: "刚刚完成了一个超酷的项目！使用了最新的前端技术栈，用户体验大幅提升！🚀",
                image: null,
                likes: 42,
                comments: 15,
                timestamp: "2小时前"
            },
            {
                id: 2,
                userId: 3,
                content: "周末去爬山了，山顶的风景太美了！推荐大家也去试试～",
                image: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80",
                likes: 128,
                comments: 36,
                timestamp: "5小时前"
            }
        ];

        // DOM 元素
        const postInput = document.getElementById('postInput');
        const likeButtons = document.querySelectorAll('.like-btn');
        const loginModal = document.getElementById('loginModal');
        const registerModal = document.getElementById('registerModal');
        const showRegister = document.getElementById('showRegister');
        const showLogin = document.getElementById('showLogin');
        const closeButtons = document.querySelectorAll('.close-modal');

        // 点赞功能
        likeButtons.forEach(button => {
            button.addEventListener('click', function() {
                const icon = this.querySelector('i');
                if (icon.classList.contains('far')) {
                    icon.classList.remove('far');
                    icon.classList.add('fas');
                    this.style.color = '#1877f2';
                } else {
                    icon.classList.remove('fas');
                    icon.classList.add('far');
                    this.style.color = '';
                }
            });
        });

        // 发帖功能
        postInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter' && this.value.trim() !== '') {
                alert(`发布动态: ${this.value}`);
                this.value = '';
            }
        });

        // 模态框控制
        function showModal(modal) {
            modal.style.display = 'flex';
        }

        function hideModal(modal) {
            modal.style.display = 'none';
        }

        // 事件监听
        showRegister.addEventListener('click', function(e) {
            e.preventDefault();
            hideModal(loginModal);
            showModal(registerModal);
        });

        showLogin.addEventListener('click', function(e) {
            e.preventDefault();
            hideModal(registerModal);
            showModal(loginModal);
        });

        closeButtons.forEach(button => {
            button.addEventListener('click', function() {
                hideModal(loginModal);
                hideModal(registerModal);
            });
        });

        // 点击模态框外部关闭
        window.addEventListener('click', function(e) {
            if (e.target === loginModal) {
                hideModal(loginModal);
            }
            if (e.target === registerModal) {
                hideModal(registerModal);
            }
        });

        // 表单提交
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('登录成功！');
            hideModal(loginModal);
        });

        document.getElementById('registerForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('注册成功！');
            hideModal(registerModal);
        });

        // 页面加载时显示登录模态框
        window.addEventListener('load', function() {
            // 在实际应用中，这里会检查用户是否已登录
            // 为了演示，我们注释掉自动显示登录模态框
            // showModal(loginModal);
        });
    </script>
</body>
</html>
