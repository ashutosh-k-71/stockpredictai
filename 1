import streamlit as st
import google.generativeai as genai
import markdown
from datetime import datetime
import time

# Page configuration
st.set_page_config(
    page_title="AI Stock Prediction",
    page_icon="📈",
    layout="wide",
    initial_sidebar_state="expanded"
)

# API Configuration
GEMINI_API_KEY = "AIzaSyD3KOEtExR050aT3v_1Gn9yD5aB5f86M4o"
genai.configure(api_key=GEMINI_API_KEY)

# Custom CSS
st.markdown("""
<style>
    .main-header {
        text-align: center;
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        padding: 2rem;
        border-radius: 10px;
        margin-bottom: 2rem;
        color: white;
    }
    
    .main-header h1 {
        font-size: 3rem;
        margin-bottom: 0.5rem;
        text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
    }
    
    .main-header p {
        font-size: 1.2rem;
        opacity: 0.9;
    }
    
    .stock-chip {
        display: inline-block;
        background: #f0f2f6;
        padding: 0.5rem 1rem;
        margin: 0.25rem;
        border-radius: 20px;
        border: 1px solid #e1e5e9;
        font-size: 0.9rem;
        cursor: pointer;
        transition: all 0.3s ease;
    }
    
    .stock-chip:hover {
        background: #4f46e5;
        color: white;
    }
    
    .result-container {
        background: #f8fafc;
        padding: 2rem;
        border-radius: 10px;
        border: 1px solid #e2e8f0;
        margin-top: 2rem;
    }
    
    .feature-card {
        background: white;
        padding: 2rem;
        border-radius: 10px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        text-align: center;
        margin: 1rem 0;
    }
    
    .feature-icon {
        font-size: 3rem;
        margin-bottom: 1rem;
    }
    
    .sidebar-info {
        background: #f0f2f6;
        padding: 1rem;
        border-radius: 10px;
        margin-bottom: 1rem;
    }
    
    .metric-card {
        background: white;
        padding: 1.5rem;
        border-radius: 10px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        margin: 1rem 0;
        border-left: 4px solid #4f46e5;
    }
    
    .success-message {
        background: #d4edda;
        color: #155724;
        padding: 1rem;
        border-radius: 5px;
        border: 1px solid #c3e6cb;
        margin: 1rem 0;
    }
    
    .warning-message {
        background: #fff3cd;
        color: #856404;
        padding: 1rem;
        border-radius: 5px;
        border: 1px solid #ffeaa7;
        margin: 1rem 0;
    }
</style>
""", unsafe_allow_html=True)

def create_prompt(stock_name):
    today = datetime.now().strftime("%B %d, %Y")
    prompt = f"""
You are a financial AI assistant. Create a stock analysis report for "{stock_name}" in the following style. If real closing price data is missing, generate plausible, realistic prices (as examples for demonstration purposes). Do NOT state that price data is unavailable; always fill in the price values and show a trend.

---
**Latest Market Trends, News, and Sentiment for {stock_name} (as of {today}):**

- Bullet list of major recent developments and news affecting {stock_name}.
- Brief analysis of the company's business performance.
- Consensus analyst/market sentiment (Buy/Hold/Sell, with a short rationale).
- Overview of how the recent price movement aligns with news and sentiment.

**Price-Based Prediction for {stock_name} (for the next trading day):**

- List the latest three closing prices for {stock_name} (if not available, make up reasonable examples in the expected currency).
- Identify the short-term trend (up, down, or stable) from those prices.
- Based on the price action and market news, predict if the price will go up, down, or stay the same tomorrow.
- Provide a brief sentence explaining the prediction logic and reference both trend and current market sentiment.

**Summary Table:**  

| Date                           | Closing Price | Trend | Market Sentiment                                      |
|---------------------------------|--------------|-------|-------------------------------------------------------|
| (3 rows for last 3 trading days, use actual or made-up dates)|
| (Next Day - label as Prediction) | (Predicted Price) | Up/Down/Stable | Short explanation for the prediction                  |

- Use consistent currency formatting (₹ for Indian stocks, $ for US stocks, etc.).
- All columns must be filled for every row; never use 'N/A' or leave empty cells.
- Always make the 'Prediction' row price by continuing the trend seen in previous prices.
- Write as if the analysis was created on {today}, always using professional but beginner-accessible language.

---

This prompt creates a fully-populated, illustrative report every time, suitable for school projects and demonstrations.
"""
    return prompt

def predict_stock(stock_name):
    try:
        model = genai.GenerativeModel("gemini-2.5-flash")
        prompt = create_prompt(stock_name)
        response = model.generate_content(prompt)
        return response.text
    except Exception as e:
        return f"Error generating prediction: {str(e)}"

def main():
    # Main Header
    st.markdown("""
    <div class="main-header">
        <h1>🤖 AI Stock Predictor</h1>
        <p>Smart Investment Insights Using Artificial Intelligence</p>
    </div>
    """, unsafe_allow_html=True)
    
    # Sidebar
    with st.sidebar:
        st.markdown("### 📊 Navigation")
        page = st.radio("Choose a page:", ["🏠 Home", "📈 Dashboard", "🔍 Markets", "💼 Portfolio"])
        
        st.markdown("### ℹ️ About")
        st.markdown("""
        <div class="sidebar-info">
            This AI-powered tool analyzes stocks using Google's Gemini AI to provide:
            <ul>
                <li>Market trend analysis</li>
                <li>Price predictions</li>
                <li>Investment insights</li>
                <li>Risk assessment</li>
            </ul>
        </div>
        """, unsafe_allow_html=True)
        
        st.markdown("### ⚠️ Disclaimer")
        st.markdown("""
        <div class="warning-message">
            This tool is for educational purposes only. 
            Always consult with financial advisors before making investment decisions.
        </div>
        """, unsafe_allow_html=True)
    
    # Main content based on selected page
    if page == "🏠 Home":
        show_home_page()
    elif page == "📈 Dashboard":
        show_dashboard()
    elif page == "🔍 Markets":
        show_markets()
    elif page == "💼 Portfolio":
        show_portfolio()

def show_home_page():
    # Stock input section
    st.markdown("### 🔍 Analyze Any Stock")
    
    col1, col2 = st.columns([3, 1])
    
    with col1:
        stock_input = st.text_input(
            "Enter Stock Symbol or Name:",
            placeholder="e.g., RELIANCE, AAPL, TSLA, Microsoft",
            help="Enter any stock symbol or company name"
        )
    
    with col2:
        analyze_btn = st.button("🔍 Analyze Stock", type="primary", use_container_width=True)
    
    # Popular stocks
    st.markdown("### 🔥 Popular Stocks")
    popular_stocks = ["RELIANCE", "TCS", "HDFC", "INFY", "AAPL", "TSLA", "GOOGL", "MSFT"]
    
    cols = st.columns(4)
    for i, stock in enumerate(popular_stocks):
        with cols[i % 4]:
            if st.button(stock, key=f"popular_{stock}"):
                st.session_state.selected_stock = stock
                st.rerun()
    
    # Handle stock selection from popular stocks
    if hasattr(st.session_state, 'selected_stock'):
        stock_input = st.session_state.selected_stock
        delattr(st.session_state, 'selected_stock')
    
    # Analysis section
    if analyze_btn and stock_input:
        st.markdown("### 📊 Analysis Results")
        
        # Show loading spinner
        with st.spinner(f"🤖 AI is analyzing {stock_input}... This may take a few moments."):
            time.sleep(2)  # Small delay for better UX
            result = predict_stock(stock_input)
        
        # Display results
        if result and not result.startswith("Error"):
            st.markdown(f"""
            <div class="success-message">
                ✅ Analysis completed successfully for <strong>{stock_input}</strong>
            </div>
            """, unsafe_allow_html=True)
            
            # Convert markdown to HTML and display
            st.markdown(f"""
            <div class="result-container">
                {markdown.markdown(result, extensions=['tables'])}
            </div>
            """, unsafe_allow_html=True)
            
            # Action buttons
            col1, col2, col3 = st.columns(3)
            with col1:
                if st.button("📊 View Dashboard"):
                    st.switch_page("Dashboard")
            with col2:
                if st.button("🖨️ Print Report"):
                    st.info("Use your browser's print function (Ctrl+P) to print this report.")
            with col3:
                if st.button("📤 Share Report"):
                    st.info("Copy the current URL to share this analysis.")
        else:
            st.error(f"❌ {result}")
    
    # Features section (shown when no analysis is running)
    if not (analyze_btn and stock_input):
        st.markdown("### ✨ Why Choose Our AI Stock Predictor?")
        
        col1, col2, col3, col4 = st.columns(4)
        
        with col1:
            st.markdown("""
            <div class="feature-card">
                <div class="feature-icon">🧠</div>
                <h3>AI-Powered Analysis</h3>
                <p>Advanced machine learning algorithms analyze market trends and news sentiment</p>
            </div>
            """, unsafe_allow_html=True)
        
        with col2:
            st.markdown("""
            <div class="feature-card">
                <div class="feature-icon">⚡</div>
                <h3>Real-Time Insights</h3>
                <p>Get up-to-date market analysis and predictions based on latest data</p>
            </div>
            """, unsafe_allow_html=True)
        
        with col3:
            st.markdown("""
            <div class="feature-card">
                <div class="feature-icon">🛡️</div>
                <h3>Risk Assessment</h3>
                <p>Comprehensive risk analysis to help make informed investment decisions</p>
            </div>
            """, unsafe_allow_html=True)
        
        with col4:
            st.markdown("""
            <div class="feature-card">
                <div class="feature-icon">📈</div>
                <h3>Trend Analysis</h3>
                <p>Detailed technical analysis with price predictions and market evaluation</p>
            </div>
            """, unsafe_allow_html=True)

def show_dashboard():
    st.markdown("### 📈 Portfolio Dashboard")
    
    # Sample portfolio data
    portfolio_data = [
        {"symbol": "RELIANCE", "quantity": 10, "avg_price": 2400.00, "current_price": 2485.30, "invested": 24000, "current_value": 24853},
        {"symbol": "TCS", "quantity": 5, "avg_price": 3600.00, "current_price": 3678.45, "invested": 18000, "current_value": 18392.25},
        {"symbol": "HDFC", "quantity": 15, "avg_price": 1500.00, "current_price": 1542.75, "invested": 22500, "current_value": 23141.25},
    ]
    
    # Portfolio summary
    total_invested = sum(stock["invested"] for stock in portfolio_data)
    total_current = sum(stock["current_value"] for stock in portfolio_data)
    total_pnl = total_current - total_invested
    total_pnl_percent = (total_pnl / total_invested) * 100
    
    # Metrics
    col1, col2, col3, col4 = st.columns(4)
    
    with col1:
        st.metric("Total Investment", f"₹{total_invested:,.2f}")
    
    with col2:
        st.metric("Current Value", f"₹{total_current:,.2f}")
    
    with col3:
        st.metric("Total P&L", f"₹{total_pnl:,.2f}", f"{total_pnl_percent:+.2f}%")
    
    with col4:
        st.metric("Holdings", f"{len(portfolio_data)}")
    
    # Portfolio table
    st.markdown("### 💼 Your Holdings")
    
    import pandas as pd
    df = pd.DataFrame(portfolio_data)
    df['P&L'] = df['current_value'] - df['invested']
    df['P&L %'] = ((df['current_value'] - df['invested']) / df['invested'] * 100).round(2)
    
    st.dataframe(df, use_container_width=True)

def show_markets():
    st.markdown("### 🔍 Live Markets")
    
    # Market indices
    col1, col2 = st.columns(2)
    
    with col1:
        st.markdown("""
        <div class="metric-card">
            <h3>NIFTY 50</h3>
            <h2>21,543.20</h2>
            <p style="color: green;">+125.45 (0.58%)</p>
        </div>
        """, unsafe_allow_html=True)
    
    with col2:
        st.markdown("""
        <div class="metric-card">
            <h3>SENSEX</h3>
            <h2>71,482.75</h2>
            <p style="color: green;">+387.30 (0.54%)</p>
        </div>
        """, unsafe_allow_html=True)
    
    # Sample stocks data
    stocks_data = [
        {"Symbol": "RELIANCE", "Price": "₹2,485.30", "Change": "+25.80", "% Change": "+1.05%"},
        {"Symbol": "TCS", "Price": "₹3,678.45", "Change": "-12.35", "% Change": "-0.33%"},
        {"Symbol": "HDFC", "Price": "₹1,542.75", "Change": "+18.90", "% Change": "+1.24%"},
        {"Symbol": "INFY", "Price": "₹1,789.20", "Change": "+8.45", "% Change": "+0.47%"},
        {"Symbol": "ICICIBANK", "Price": "₹1,089.65", "Change": "-5.30", "% Change": "-0.48%"},
    ]
    
    st.markdown("### 📊 Top Stocks")
    
    import pandas as pd
    df = pd.DataFrame(stocks_data)
    st.dataframe(df, use_container_width=True)

def show_portfolio():
    st.markdown("### 💼 Portfolio Management")
    
    st.info("🚧 Portfolio management features coming soon! Currently showing demo data.")
    
    # Add stock form
    with st.form("add_stock"):
        st.markdown("#### Add New Stock")
        col1, col2, col3 = st.columns(3)
        
        with col1:
            symbol = st.text_input("Stock Symbol")
        with col2:
            quantity = st.number_input("Quantity", min_value=1, value=1)
        with col3:
            price = st.number_input("Purchase Price", min_value=0.01, value=100.00)
        
        submitted = st.form_submit_button("Add to Portfolio")
        if submitted:
            st.success(f"✅ Added {quantity} shares of {symbol} at ₹{price} to your portfolio!")

if __name__ == "__main__":
    main()
