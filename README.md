# AI Scam Shield - MongoDB Integration

A Next.js application with MongoDB authentication for AI-powered scam detection and cybersecurity protection.

## 🚀 Features

- **User Authentication**: Complete signup/login system with MongoDB
- **AI Scam Analysis**: Google Gemini AI integration for content analysis
- **User Dashboard**: Personalized dashboard with analysis history
- **Cybercrime Reporting**: Secure reporting system for cybercrime incidents
- **Profile Management**: User profile with statistics and settings

## 🛠️ Tech Stack

- **Frontend**: Next.js 14, React 18, TypeScript
- **Database**: MongoDB with Mongoose
- **Authentication**: JWT tokens with HTTP-only cookies
- **AI**: Google Generative AI (Gemini 2.0)
- **Styling**: Tailwind CSS + Custom CSS
- **UI Components**: Radix UI (shadcn/ui)

## 📋 Prerequisites

- Node.js 18+ installed
- MongoDB database (local or MongoDB Atlas)
- Google AI API key

## 🔧 Installation & Setup

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd SIH-Cyber-project
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Variables**
   Create a `.env.local` file in the root directory:
   ```env
   # MongoDB Connection
   MONGODB_URI=mongodb://localhost:27017/ai-scam-shield
   # For MongoDB Atlas: mongodb+srv://username:password@cluster.mongodb.net/ai-scam-shield
   
   # JWT Secret (Generate a strong secret key)
   JWT_SECRET=your-super-secret-jwt-key-here-make-it-long-and-random
   
   # Google AI API Key
   GOOGLE_API_KEY=your-google-api-key-here
   
   # Environment
   NODE_ENV=development
   ```

4. **MongoDB Setup**
   
   **Option A: Local MongoDB**
   - Install MongoDB locally
   - Start MongoDB service
   - Use: `MONGODB_URI=mongodb://localhost:27017/ai-scam-shield`
   
   **Option B: MongoDB Atlas (Recommended)**
   - Create account at [MongoDB Atlas](https://www.mongodb.com/atlas)
   - Create a new cluster
   - Get connection string and replace in `.env.local`
   - Whitelist your IP address

5. **Google AI API Key**
   - Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Create a new API key
   - Add it to your `.env.local` file

6. **Run the development server**
   ```bash
   npm run dev
   ```

7. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## 🔐 Authentication Flow

1. **New Users**: Visit `/auth` → Sign Up → Automatic login
2. **Existing Users**: Visit `/auth` → Sign In
3. **Protected Routes**: All main pages require authentication
4. **Logout**: Click logout button in header

## 📁 Project Structure

```
├── app/
│   ├── api/auth/          # Authentication API routes
│   ├── auth/              # Login/Signup page
│   ├── calculator/        # AI analysis tool
│   ├── profile/           # User profile & settings
│   ├── report/            # Cybercrime reporting
│   └── page.tsx           # Dashboard/Home
├── components/ui/         # Reusable UI components
├── hooks/                 # Custom React hooks
├── lib/                   # Utility functions
├── models/                # MongoDB models
└── types/                 # TypeScript types
```

## 🔒 Security Features

- **Password Hashing**: bcryptjs with salt rounds
- **JWT Tokens**: Secure authentication with HTTP-only cookies
- **Input Validation**: Server-side validation for all inputs
- **Protected Routes**: Authentication required for all main features
- **Environment Variables**: Sensitive data stored securely

## 🎯 Usage

1. **Sign Up/Login**: Create account or login at `/auth`
2. **Dashboard**: View scam alerts and navigate features
3. **Analyze Content**: Use `/calculator` to check suspicious emails/messages
4. **View Profile**: Check your statistics and analysis history at `/profile`
5. **Report Scams**: Submit cybercrime reports at `/report`

## 🚨 Password Requirements

- Minimum 6 characters
- At least 1 uppercase letter
- At least 1 lowercase letter  
- At least 1 number

## 🔧 API Endpoints

- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `GET /api/auth/me` - Get current user
- `POST /api/analyze` - AI content analysis

## 🐛 Troubleshooting

**MongoDB Connection Issues:**
- Check your MongoDB URI in `.env.local`
- Ensure MongoDB service is running (local)
- Check network access in MongoDB Atlas

**Authentication Issues:**
- Clear browser cookies
- Check JWT_SECRET in environment variables
- Verify API endpoints are working

**AI Analysis Issues:**
- Verify Google API key is valid
- Check API quota limits
- Ensure content is not too long (10k chars max)

## 📝 Development Notes

- User data is automatically populated in forms
- Real-time authentication state management
- Responsive design for all screen sizes
- Error handling with user-friendly messages
- Loading states for better UX

## 🚀 Deployment

1. **Environment Variables**: Set all required env vars in production
2. **Database**: Use MongoDB Atlas for production
3. **Security**: Ensure HTTPS in production for secure cookies
4. **Build**: Run `npm run build` before deployment

## 📄 License

This project is part of Smart India Hackathon (SIH) cybersecurity initiative.