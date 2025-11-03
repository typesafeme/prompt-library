You’re aiming to build a US-market portfolio app focused on stocks and options, with a screener, watchlist, charts, and search by ticker or company name. No backend is required beyond Auth0 for authentication. You want a modern, Robinhood-like UX, responsive for phone and tablet (iOS and Android), using shadcn components. You also asked for a spec library (prompt library) to guide development and a clarification on anything else to add.
Prompt Library: Brilliant UX Spec for a US Market Portfolio App
	•	Objective
	•	Create a highly responsive, mobile-first single-page app (SPA) that supports stocks and options with a rich screener, dynamic watchlist, interactive charts, and fast search by ticker or company name. No backend is required beyond Auth0 for authentication. Implement UI using shadcn components to achieve a Robinhood-inspired experience.
	•	Core Features
	•	Authentication
	•	Integrate Auth0 for authentication with social login options (Google, Apple, etc.) and email/password.
	•	Include secure session handling and seamless sign-in/sign-out flows.
	•	Home Dashboard
	•	Summary cards: net worth, day gain/loss, positions value, cash balance (mocked if no backend).
	•	Quick actions: Buy/Sell (as placeholders), Add to Watchlist, Filter by Asset Type.
	•	Screener
	•	Configurable screens: market cap, sector, P/E, dividend yield, momentum, volume, options liquidity.
	•	Real-time-ish (cached) OHLCV data display, sortable by multiple fields.
	•	Saveable presets and shareable screener URLs (encode settings).
	•	Watchlist
	•	Multi-portfolio support (Personal, Iris/Simulated, etc.).
	•	Real-time price updates (simulated if no backend) with percent change, intraday moves.
	•	Quick actions from list: add to positions, remove, set alerts (synthetic).
	•	Charting
	•	Interactive charts with candlestick/line views, timeframes (1D, 1W, 1M, 3M, 1Y, YTD).
	•	Overlay indicators: SMA, EMA, RSI, MACD; ability to add/remove indicators.
	•	Ticker search-initiated chart updates with symbol tooltip and crosshair.
	•	Security Details
	•	Ticker/name search with autocomplete; show description, exchange, sector, financials, earnings date.
	•	Options view: chain view with strike, expiry, volume, implied volatility (mocked if no backend).
	•	Search
	•	Global search by ticker or company name; fast indexing with fuzzy matching; keyboard shortcuts.
	•	UI/UX
	•	Robinhood-like aesthetic with clean typography, airy spacing, light/dark mode, accessible color contrast.
	•	Responsive layout: mobile (tabs/navigation bottom), tablet (two-column), desktop (three-column.
	•	Keyboard accessibility and ARIA roles.
	•	Design System and Components (Shadcn)
	•	Use shadcn/ui primitives for: Button, Input, Select, DropdownMenu, Tabs, Card, Avatar, Badge, Tooltip, Dialog, Sheet, Carousel, Chart canvas wrapper, Grid, Table.
	•	Typography and color tokens aligned with modern fintech aesthetics.
	•	Responsive grid: ensure charts and lists resize gracefully across breakpoints.
	•	Data and State Management
	•	Data layer should be decoupled from UI: use a mock data service that can be swapped with a real backend later.
	•	Provide a mock API layer that serves:
	•	Ticker metadata (name, sector, exchange)
	•	OHLCV data per symbol
	•	Options chain data per ticker
	•	Screener results and filters
	•	State management: lightweight store (e.g., Zustand or React context) to manage:
	•	auth status, user preferences
	•	watchlists, portfolios, screener presets
	•	UI state: active tab, selected symbol, chart timeframe, indicators
	•	Accessibility and UX Considerations
	•	Ensure all interactive elements are reachable via keyboard.
	•	Provide meaningful aria-labels and screen-reader text.
	•	Include motion-reduction options and high-contrast themes if needed.
	•	Performance and Responsiveness
	•	Lazy-load heavy components (charts, charts data) as they comeinto view.
	•	Debounce search input; provide instant visual feedback.
	•	Optimize for low-bandwidth scenarios with compact data rendering.
	•	Security and Compliance
	•	Do not hard-code real trading actions; simulate trades for UI/UX unless backend is provided.
	•	Ensure Auth0 integration uses recommended PKCE for mobile platforms.
	•	Do not log sensitive user data; implement basic client-side data isolation for mock data.
	•	Milestones and Deliverables
	•	Milestone 1: Wireframes and design system adaptation with shadcn components; static prototype for mobile and tablet.
	•	Milestone 2: Mock data services and screener/watchlist interfaces; charting ready with indicators.
	•	Milestone 3: Auth0 integration and responsive polishing; accessibility review.
	•	Milestone 4: Local offline-capable mode with mock data persistence (localStorage); demonstration of full flow.
	•	Optional Enhancements (if scope allows)
	•	Offline mode caching for charts and screener results.
	•	Theme customization with brandable color schemes.
	•	Gesture support: swipe to navigate tabs, pinching to zoom chart (where feasible).
	•	Figma-to-code assets and export guidelines.
	•	Architecture Sketch (High-Level)
	•	Frontend: React + TypeScript
	•	UI Layer: shadcn components
	•	State: Zustand store
	•	Data: Mock API layer with in-memory data, GraphQL or REST-like endpoints
	•	Auth: Auth0 SDK
	•	Styling: Tailwind CSS with shadcn presets
	
Clarifications Sought	
  
  Multiple screen sizes
	•	Include explicit mockups for phone and tablet breakpoints.
	•	Provide responsive layouts that adapt from single-column mobile views to two- and three-column tablet/desktop arrangements.
	•	Sample JSON payloads
	•	Include representative payloads for screener presets.
	•	Provide a few example tickers with metadata (ticker, name, sector, exchange) to seed the mock data service.
	•	Lightweight mobile navigation pattern
	•	Use bottom tab navigation for primary sections (Screener, Watchlist, Chart, Search/Explore).
	•	Include a collapsible top bar or bottom sheet for secondary actions (Settings, Alerts, Help).
	•	Ensure gesture support where feasible (swipe between tabs, pull-to-refresh).
