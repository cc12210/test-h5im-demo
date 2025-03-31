<p align="center">
    <a href="https://openim.io">
        <img src="./docs/images/logo.jpg" width="60%" height="30%"/>
    </a>
</p>

# OpenIM H5 💬💻

<p>
  <a href="https://docs.openim.io/">OpenIM Docs</a>
  •
  <a href="https://github.com/openimsdk/open-im-server">OpenIM Server</a>
  •
  <a href="https://github.com/openimsdk/openim-sdk-js-wasm">openim-sdk-wasm</a>
  •
  <a href="https://github.com/openimsdk/openim-sdk-core">openim-sdk-core</a>
</p>

OpenIM provides an open-source Instant Messaging (IM) SDK for developers, serving as an alternative solution to cloud services like Twilio and Sendbird. With OpenIM, developers can build secure and reliable IM applications similar to WeChat, Zoom, and Slack.

This warehouse is based on the open source version of OpenIM SDK development, provides a Vue based instant messaging application. You can use this application as a reference implementation of the OpenIM SDK. This project refers to `@openim/wasm-client-sdk`, the Web version of the SDK for building Web applications.

<p align="center">
   <img src="./docs/images/preview.png" alt="Preview" width="32%"/>
   <span style="display: inline-block; width: 16px;"></span>
   <img src="./docs/images/preview2.png" alt="Preview" width="32%"/>
</p>

## License :page_facing_up:

This repository adopts the GNU Affero General Public License v3 (AGPL-3.0) with additional terms. **Commercial use is not permitted.** For more details, please refer to [here](./LICENSE).

## Development Environment

Before you start developing, please ensure that your system has the following software installed:

- **Node.js**: Version ≥ 16.x ([manual installation](https://nodejs.org/dist/latest-v20.x/) or via [nvm](https://github.com/nvm-sh/nvm))
- **npm**: Version ≥ 6.x (installed with Node.js)
- **Git**: For version control

You also need to have the latest version of the [OpenIM Server deployed](https://docs.openim.io/zh-Hans/guides/gettingStarted/dockerCompose). After that, you can compile this project and connect it to your own server for testing.

## Runtime Environment

This application supports the following browsers and operating system versions:

| Browser/OS  | Version              | Status |
| ----------- | -------------------- | ------ |
| **Chrome**  | 78 and above         | ✅     |

### Note

- **Chrome**: It is recommended to use the latest version for the best experience.

## Quick Start

Follow these steps to set up your local development environment:

1. Clone the repository

   ```bash
   git clone https://github.com/openimsdk/openim-h5-demo.git
   cd openim-h5-demo
   ```

2. Install dependencies

   ```bash
   npm install
   ```

3. Modify the configuration

   - In the `config/dev.env.ts` and `config/pord.env.ts` file:

     > If you haven't changed the default server port, simply change `BASE_HOST` to your server IP. If you need to set up a domain and HTTPS access, please refer to [nginx configuration](https://docs.openim.io/zh-Hans/guides/gettingStarted/nginxDomainConfig), use the configuration at the bottom, and modify `BASE_DOMAIN` to your domain name.

     ```javascript
     const BASE_HOST = 'your-server-ip'
     const CHAT_URL = `http://${BASE_HOST}:10008`
     const API_URL = `http://${BASE_HOST}:10002`
     const WS_URL = `ws://${BASE_HOST}:10001`

     // const BASE_DOMAIN = 'your-server-domain'
     // const CHAT_URL = `http://${BASE_DOMAIN}/chat`
     // const API_URL = `http://${BASE_DOMAIN}/api`
     // const WS_URL = `ws://${BASE_DOMAIN}/msg_gateway`
     ```

4. Run `npm run dev` to start the development server. Access [http://localhost:3003](http://localhost:3003) to view the result.

5. Start developing and testing! 🎉

## Audio/Video Calls

The open-source version supports one-to-one audio and video calls. You need to first deploy and configure the [server](https://github.com/openimsdk/chat/blob/main/HOW_TO_SETUP_LIVEKIT_SERVER.md). For multi-party audio/video calls or video conferencing, please contact us at [contact@openim.io](mailto:contact@openim.io).

## Build 🚀

### Web Application

1. Run the following command to build the Web application:
   ```bash
   npm run build
   ```
2. The build artifacts will be located in the `dist` directory.

## Features

### Description

| Feature Module             | Feature                                                                          | Status |
| -------------------------- | -------------------------------------------------------------------------------- | ------ |
| **Account Features**       | Phone number registration \ Email registration \ Verification code login         | ✅     |
|                            | View \ Edit personal information                                                 | ✅     |
|                            | Multi-language settings                                                          | ✅     |
|                            | Change password \ Forgot password                                                | ✅     |
| **Friend Features**        | Find \ Apply \ Search \ Add \ Delete friends                                     | ✅     |
|                            | Accept \ Reject friend requests                                                  | ✅     |
|                            | Friend notes                                                                     | ✅     |
|                            | Allow friend requests or not                                                     | ✅     |
|                            | Friend list \ Friend data real-time syncing                                      | ✅     |
| **Blocklist**              | Restrict messages                                                                | ✅     |
|                            | Real-time syncing of blocklist                                                   | ✅     |
|                            | Add \ Remove from blocklist                                                      | ✅     |
| **Group Features**         | Create \ Dismiss groups                                                          | ✅     |
|                            | Apply to join \ Invite to join \ Leave group \ Remove members                    | ✅     |
|                            | Group name / Avatar changes / Group data updates (notifications, real-time sync) | ✅     |
|                            | Invite members to group                                                          | ✅     |
|                            | Transfer group ownership                                                         | ✅     |
|                            | Group owner or admin approve join requests                                       | ✅     |
|                            | Search group members                                                             | ✅     |
| **Message Features**       | Offline messages                                                                 | ✅     |
|                            | Roaming messages                                                                 | ✅     |
|                            | Multi-end messages                                                               | ✅     |
|                            | Message history                                                                  | ✅     |
|                            | Message deletion                                                                 | ✅     |
|                            | Clear messages                                                                   | ✅     |
|                            | Copy messages                                                                    | ✅     |
|                            | Typing indicator in single chat                                                  | ✅     |
|                            | Do Not Disturb for new messages                                                  | ✅     |
|                            | Clear chat history                                                               | ✅     |
|                            | New members can view group chat history                                          | ✅     |
|                            | New message reminders                                                            | ✅     |
|                            | Text messages                                                                    | ✅     |
|                            | Image messages                                                                   | ✅     |
|                            | Video messages                                                                   | ✅     |
|                            | Emoji messages                                                                   | ✅     |
|                            | File messages                                                                    | ✅     |
|                            | Voice messages                                                                   | ✅     |
|                            | Contact card messages                                                            | ✅     |
|                            | Location messages                                                                | ✅     |
|                            | Custom messages                                                                  | ✅     |
| **Conversation**           | Pin conversation                                                                 | ✅     |
|                            | Mark conversation as read                                                        | ✅     |
|                            | Mute conversation                                                                | ✅     |
| **REST API**               | Authentication management                                                        | ✅     |
|                            | User management                                                                  | ✅     |
|                            | Relationship chain management                                                    | ✅     |
|                            | Group management                                                                 | ✅     |
|                            | Conversation management                                                          | ✅     |
|                            | Message management                                                               | ✅     |
| **Webhook**                | Group callbacks                                                                  | ✅     |
|                            | Message callbacks                                                                | ✅     |
|                            | Push callbacks                                                                   | ✅     |
|                            | Relationship callbacks                                                           | ✅     |
|                            | User callbacks                                                                   | ✅     |
| **Capacity & Performance** | 10,000 friends                                                                   | ✅     |
|                            | 100,000-member supergroup                                                        | ✅     |
|                            | Second-level syncing                                                             | ✅     |
|                            | Cluster deployment                                                               | ✅     |
|                            | Multi-device kick-out strategy                                                   |        |
| **Online Status**          | No mutual kick-out across all platforms                                          | ✅     |
|                            | Each platform can only log in with one device                                    | ✅     |
|                            | PC, Mobile, Pad, Web, Mini Program each can log in with one device               | ✅     |
|                            | PC not mutually kicked, only one device total for other platforms                | ✅     |
| **Audio/Video Call**       | One-to-one audio and video calls                                                 | ✅     |
| **File Storage**           | Supports private Minio deployment                                                | ✅     |
|                            | Supports public cloud services COS, OSS, Kodo, S3                                | ✅     |
| **Push**                   | Real-time online message push                                                    | ✅     |
|                            | Offline message push, supports Getui, Firebase                                   | ✅     |

For more advanced features, audio/video calls, or video conferences, please contact us at [contact@openim.io](mailto:contact@openim.io).

## Join Our Community :busts_in_silhouette:

- 🚀 [Join our Slack community](https://join.slack.com/t/openimsdk/shared_invite/zt-22720d66b-o_FvKxMTGXtcnnnHiMqe9Q)
- :eyes: [Join our WeChat group](https://openim-1253691595.cos.ap-nanjing.myqcloud.com/WechatIMG20.jpeg)

## FAQ

1. **When publishing to the web, how to solve slow WASM loading?**

   Answer: Use gzip compression on the WASM file to significantly reduce the size. You can also leverage a CDN to accelerate loading.
