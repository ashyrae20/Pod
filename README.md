"homepage": "https://ashyrae20.github.io/your-repo-name",
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build"
}
export const config = {
  apiKey: process.env.REACT_APP_GEMINI_API_KEY,
  environment: process.env.REACT_APP_ENVIRONMENT || 'development',
  version: process.env.REACT_APP_VERSION || '1.0.0',
  apiUrl: 'https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent',
  isDevelopment: process.env.REACT_APP_ENVIRONMENT === 'development',
  isProduction: process.env.REACT_APP_ENVIRONMENT === 'production'
};
export const validateConfig = () => {
  const errors = [];
  
  if (!config.apiKey) {
    errors.push('REACT_APP_GEMINI_API_KEY is required');
  }
  
  if (errors.length > 0) {
    console.error('Configuration errors:', errors);
    return false;
  }
  
  return true;
};
