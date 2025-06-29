import React, { useState, useEffect } from 'react';
import { Home, User, Laptop, Folder, Mail } from 'lucide-react'; // Importing icons from lucide-react

// Main App component
const App = () => {
  const [activeSection, setActiveSection] = useState('home');

  // Smooth scroll function for navigation
  const scrollToSection = (id) => {
    const element = document.getElementById(id);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
      setActiveSection(id);
    }
  };

  return (
    <div className="min-h-screen bg-gray-950 font-inter text-gray-200 antialiased">
      {/* Navigation Bar - Sleek style */}
      <nav className="fixed top-0 left-0 right-0 z-50 bg-gray-900 border-b border-green-600 shadow-xl p-4 flex justify-center items-center">
        <ul className="flex space-x-6 md:space-x-10">
          <li>
            <button
              onClick={() => scrollToSection('home')}
              className={`flex items-center p-3 rounded-full transition-all duration-300 ${
                activeSection === 'home' ? 'bg-green-700 text-white shadow-md' : 'text-gray-400 hover:text-green-400 hover:bg-gray-800'
              }`}
              aria-label="Go to Home section"
            >
              <Home className="w-5 h-5 mr-1 md:mr-2" />
              <span className="hidden md:inline text-sm font-medium">HOME</span>
            </button>
          </li>
          <li>
            <button
              onClick={() => scrollToSection('about')}
              className={`flex items-center p-3 rounded-full transition-all duration-300 ${
                activeSection === 'about' ? 'bg-green-700 text-white shadow-md' : 'text-gray-400 hover:text-green-400 hover:bg-gray-800'
              }`}
              aria-label="Go to About section"
            >
              <User className="w-5 h-5 mr-1 md:mr-2" />
              <span className="hidden md:inline text-sm font-medium">ABOUT</span>
            </button>
          </li>
          <li>
            <button
              onClick={() => scrollToSection('skills')}
              className={`flex items-center p-3 rounded-full transition-all duration-300 ${
                activeSection === 'skills' ? 'bg-green-700 text-white shadow-md' : 'text-gray-400 hover:text-green-400 hover:bg-gray-800'
              }`}
              aria-label="Go to Skills section"
            >
              <Laptop className="w-5 h-5 mr-1 md:mr-2" />
              <span className="hidden md:inline text-sm font-medium">SKILLS</span>
            </button>
          </li>
          <li>
            <button
              onClick={() => scrollToSection('projects')}
              className={`flex items-center p-3 rounded-full transition-all duration-300 ${
                activeSection === 'projects' ? 'bg-green-700 text-white shadow-md' : 'text-gray-400 hover:text-green-400 hover:bg-gray-800'
              }`}
              aria-label="Go to Projects section"
            >
              <Folder className="w-5 h-5 mr-1 md:mr-2" />
              <span className="hidden md:inline text-sm font-medium">PROJECTS</span>
            </button>
          </li>
          <li>
            <button
              onClick={() => scrollToSection('contact')}
              className={`flex items-center p-3 rounded-full transition-all duration-300 ${
                activeSection === 'contact' ? 'bg-green-700 text-white shadow-md' : 'text-gray-400 hover:text-green-400 hover:bg-gray-800'
              }`}
              aria-label="Go to Contact section"
            >
              <Mail className="w-5 h-5 mr-1 md:mr-2" />
              <span className="hidden md:inline text-sm font-medium">CONTACT</span>
            </button>
          </li>
        </ul>
      </nav>

      <main className="pt-20"> {/* Padding top to avoid content hidden by fixed nav */}
        {/* Home Section - Sleek style */}
        <section id="home" className="flex flex-col items-center justify-center min-h-screen text-center bg-gradient-to-br from-gray-950 to-gray-800 text-white p-8 rounded-b-xl shadow-2xl">
          <div className="w-32 h-32 md:w-48 md:h-48 rounded-full overflow-hidden mb-6 border-4 border-green-600 shadow-lg animate-fade-in">
            <img
              src="https://placehold.co/400x400/1C2833/00B894?text=YOUR+FACE"
              alt="Your Profile"
              className="w-full h-full object-cover"
              onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/400x400/1C2833/00B894?text=Placeholder"; }}
            />
          </div>
          <h1 className="text-4xl md:text-6xl font-extrabold mb-4 text-green-500 animate-scale-in">Hello, I'm [Your Name]!</h1>
          <p className="text-xl md:text-2xl mb-8 animate-fade-in-up text-gray-300">A <span className="text-green-400 font-semibold">Software Engineer</span> specializing in <span className="text-green-400 font-semibold">Web Development</span>.</p>
          <button
            onClick={() => scrollToSection('projects')}
            className="bg-green-600 text-white px-8 py-3 rounded-full text-lg font-semibold shadow-xl hover:bg-green-700 transition-all duration-300 transform hover:scale-105 animate-fade-in-up delay-400"
          >
            Explore My Work
          </button>
        </section>

        {/* About Section - Sleek style */}
        <section id="about" className="py-20 px-8 bg-gray-900 shadow-xl rounded-xl m-4 md:m-8 border border-gray-700">
          <div className="max-w-4xl mx-auto text-center">
            <h2 className="text-4xl font-bold text-green-500 mb-8">About Me</h2>
            <div className="flex flex-col md:flex-row items-center gap-8">
              <div className="md:w-1/3 flex-shrink-0 animate-fade-in-left">
                <img
                  src="https://placehold.co/300x300/2C3E50/00B894?text=About+Me"
                  alt="About Me"
                  className="w-full h-auto rounded-lg shadow-lg"
                  onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/300x300/2C3E50/00B894?text=Placeholder"; }}
                />
              </div>
              <div className="md:w-2/3 text-lg text-gray-300 text-left animate-fade-in-right">
                <p className="mb-4">
                  Hello! I'm [Your Name], a dedicated <span className="text-green-400 font-medium">Software Engineer</span> with a passion for crafting efficient and elegant digital solutions.
                  My journey in web development began [Number] years ago, and I've been continuously evolving my skills to stay at the forefront of technology.
                </p>
                <p className="mb-4">
                  I specialize in modern web technologies including <span className="text-green-400 font-medium">React, Node.js, and Python</span>, focusing on building scalable and user-centric applications.
                  Outside of coding, I enjoy [mention a hobby, e.g., exploring new tech gadgets, photography, cycling].
                  I'm always keen to connect on exciting projects and contribute to a better digital landscape.
                </p>
                <p>
                  Feel free to browse my work and reach out if you'd like to collaborate!
                </p>
              </div>
            </div>
          </div>
        </section>

        {/* Skills Section - Sleek style */}
        <section id="skills" className="py-20 px-8 bg-gray-950 shadow-xl rounded-xl m-4 md:m-8 border border-gray-700">
          <div className="max-w-4xl mx-auto text-center">
            <h2 className="text-4xl font-bold text-green-500 mb-8">My Skills</h2>
            <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
              {/* Example Skill Card */}
              <div className="bg-gray-900 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1 hover:border-green-600 border border-gray-800">
                <img src="https://placehold.co/80x80/2C3E50/00B894?text=React" alt="React Logo" className="w-20 h-20 mx-auto mb-4" onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/80x80/2C3E50/00B894?text=React"; }} />
                <h3 className="text-xl font-semibold text-green-400">React.js</h3>
              </div>
              <div className="bg-gray-900 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1 hover:border-green-600 border border-gray-800">
                <img src="https://placehold.co/80x80/2C3E50/00B894?text=Tailwind" alt="Tailwind CSS Logo" className="w-20 h-20 mx-auto mb-4" onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/80x80/2C3E50/00B894?text=Tailwind"; }} />
                <h3 className="text-xl font-semibold text-green-400">Tailwind CSS</h3>
              </div>
              <div className="bg-gray-900 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1 hover:border-green-600 border border-gray-800">
                <img src="https://placehold.co/80x80/2C3E50/00B894?text=JS" alt="JavaScript Logo" className="w-20 h-20 mx-auto mb-4" onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/80x80/2C3E50/00B894?text=JS"; }} />
                <h3 className="text-xl font-semibold text-green-400">JavaScript</h3>
              </div>
              <div className="bg-gray-900 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1 hover:border-green-600 border border-gray-800">
                <img src="https://placehold.co/80x80/2C3E50/00B894?text=HTML" alt="HTML5 Logo" className="w-20 h-20 mx-auto mb-4" onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/80x80/2C3E50/00B894?text=HTML"; }} />
                <h3 className="text-xl font-semibold text-green-400">HTML5</h3>
              </div>
              <div className="bg-gray-900 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1 hover:border-green-600 border border-gray-800">
                <img src="https://placehold.co/80x80/2C3E50/00B894?text=CSS" alt="CSS3 Logo" className="w-20 h-20 mx-auto mb-4" onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/80x80/2C3E50/00B894?text=CSS"; }} />
                <h3 className="text-xl font-semibold text-green-400">CSS3</h3>
              </div>
              <div className="bg-gray-900 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1 hover:border-green-600 border border-gray-800">
                <img src="https://placehold.co/80x80/2C3E50/00B894?text=Node" alt="Node.js Logo" className="w-20 h-20 mx-auto mb-4" onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/80x80/2C3E50/00B894?text=Node"; }} />
                <h3 className="text-xl font-semibold text-green-400">Node.js</h3>
              </div>
              <div className="bg-gray-900 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1 hover:border-green-600 border border-gray-800">
                <img src="https://placehold.co/80x80/2C3E50/00B894?text=Python" alt="Python Logo" className="w-20 h-20 mx-auto mb-4" onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/80x80/2C3E50/00B894?text=Python"; }} />
                <h3 className="text-xl font-semibold text-green-400">Python</h3>
              </div>
              <div className="bg-gray-900 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1 hover:border-green-600 border border-gray-800">
                <img src="https://placehold.co/80x80/2C3E50/00B894?text=Git" alt="Git Logo" className="w-20 h-20 mx-auto mb-4" onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/80x80/2C3E50/00B894?text=Git"; }} />
                <h3 className="text-xl font-semibold text-green-400">Git & GitHub</h3>
              </div>
            </div>
          </div>
        </section>

        {/* Projects Section - Sleek style */}
        <section id="projects" className="py-20 px-8 bg-gray-900 shadow-xl rounded-xl m-4 md:m-8 border border-gray-700">
          <div className="max-w-5xl mx-auto text-center">
            <h2 className="text-4xl font-bold text-green-500 mb-8">My Projects</h2>
            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
              {/* Example Project Card */}
              <div className="bg-gray-950 rounded-lg shadow-md overflow-hidden hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-2 hover:border-green-600 border border-gray-800">
                <img
                  src="https://placehold.co/600x400/212F3C/00B894?text=Project+One"
                  alt="Project One"
                  className="w-full h-48 object-cover"
                  onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/600x400/212F3C/00B894?text=Project+One"; }}
                />
                <div className="p-6">
                  <h3 className="text-2xl font-semibold text-green-400 mb-2">Project Title One</h3>
                  <p className="text-gray-300 mb-4">
                    A brief description of Project One. This project showcases [key technologies] and solves [problem].
                  </p>
                  <div className="flex justify-center space-x-4">
                    <a
                      href="#"
                      target="_blank"
                      rel="noopener noreferrer"
                      className="inline-block bg-green-600 text-white px-5 py-2 rounded-full text-sm font-semibold hover:bg-green-700 transition-colors duration-300"
                    >
                      View Live
                    </a>
                    <a
                      href="#"
                      target="_blank"
                      rel="noopener noreferrer"
                      className="inline-block bg-gray-700 text-gray-200 px-5 py-2 rounded-full text-sm font-semibold hover:bg-gray-800 transition-colors duration-300"
                    >
                      GitHub Repo
                    </a>
                  </div>
                </div>
              </div>

              {/* Repeat for more projects */}
              <div className="bg-gray-950 rounded-lg shadow-md overflow-hidden hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-2 hover:border-green-600 border border-gray-800">
                <img
                  src="https://placehold.co/600x400/212F3C/00B894?text=Project+Two"
                  alt="Project Two"
                  className="w-full h-48 object-cover"
                  onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/600x400/212F3C/00B894?text=Project+Two"; }}
                />
                <div className="p-6">
                  <h3 className="text-2xl font-semibold text-green-400 mb-2">Project Title Two</h3>
                  <p className="text-gray-300 mb-4">
                    A brief description of Project Two. This project demonstrates [key technologies] and addresses [problem].
                  </p>
                  <div className="flex justify-center space-x-4">
                    <a
                      href="#"
                      target="_blank"
                      rel="noopener noreferrer"
                      className="inline-block bg-green-600 text-white px-5 py-2 rounded-full text-sm font-semibold hover:bg-green-700 transition-colors duration-300"
                    >
                      View Live
                    </a>
                    <a
                      href="#"
                      target="_blank"
                      rel="noopener noreferrer"
                      className="inline-block bg-gray-700 text-gray-200 px-5 py-2 rounded-full text-sm font-semibold hover:bg-gray-800 transition-colors duration-300"
                    >
                      GitHub Repo
                    </a>
                  </div>
                </div>
              </div>

              <div className="bg-gray-950 rounded-lg shadow-md overflow-hidden hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-2 hover:border-green-600 border border-gray-800">
                <img
                  src="https://placehold.co/600x400/212F3C/00B894?text=Project+Three"
                  alt="Project Three"
                  className="w-full h-48 object-cover"
                  onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/600x400/212F3C/00B894?text=Project+Three"; }}
                />
                <div className="p-6">
                  <h3 className="text-2xl font-semibold text-green-400 mb-2">Project Title Three</h3>
                  <p className="text-gray-300 mb-4">
                    A brief description of Project Three. This project explores [key technologies] and implements [solution].
                  </p>
                  <div className="flex justify-center space-x-4">
                    <a
                      href="#"
                      target="_blank"
                      rel="noopener noreferrer"
                      className="inline-block bg-green-600 text-white px-5 py-2 rounded-full text-sm font-semibold hover:bg-green-700 transition-colors duration-300"
                    >
                      View Live
                    </a>
                    <a
                      href="#"
                      target="_blank"
                      rel="noopener noreferrer"
                      className="inline-block bg-gray-700 text-gray-200 px-5 py-2 rounded-full text-sm font-semibold hover:bg-gray-800 transition-colors duration-300"
                    >
                      GitHub Repo
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        {/* Contact Section - Sleek style */}
        <section id="contact" className="py-20 px-8 bg-gray-950 shadow-xl rounded-xl m-4 md:m-8 border border-gray-700">
          <div className="max-w-xl mx-auto text-center">
            <h2 className="text-4xl font-bold text-green-500 mb-8">Get In Touch</h2>
            <p className="text-lg text-gray-300 mb-8">
              I'm always open to new opportunities and collaborations. Feel free to reach out!
            </p>
            <form className="bg-gray-900 p-8 rounded-lg shadow-md border border-gray-800">
              <div className="mb-6">
                <label htmlFor="name" className="block text-left text-green-400 text-sm font-medium mb-2">
                  Name
                </label>
                <input
                  type="text"
                  id="name"
                  name="name"
                  className="shadow-inner appearance-none border border-gray-700 rounded-md w-full py-3 px-4 bg-gray-800 text-gray-200 leading-tight focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent transition-all duration-300"
                  placeholder="Your Name"
                  required
                />
              </div>
              <div className="mb-6">
                <label htmlFor="email" className="block text-left text-green-400 text-sm font-medium mb-2">
                  Email
                </label>
                <input
                  type="email"
                  id="email"
                  name="email"
                  className="shadow-inner appearance-none border border-gray-700 rounded-md w-full py-3 px-4 bg-gray-800 text-gray-200 leading-tight focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent transition-all duration-300"
                  placeholder="your.email@example.com"
                  required
                />
              </div>
              <div className="mb-6">
                <label htmlFor="message" className="block text-left text-green-400 text-sm font-medium mb-2">
                  Message
                </label>
                <textarea
                  id="message"
                  name="message"
                  rows="6"
                  className="shadow-inner appearance-none border border-gray-700 rounded-md w-full py-3 px-4 bg-gray-800 text-gray-200 leading-tight focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent transition-all duration-300"
                  placeholder="Your message..."
                  required
                ></textarea>
              </div>
              <button
                type="submit"
                className="bg-green-600 text-white px-8 py-3 rounded-full text-lg font-semibold shadow-md hover:bg-green-700 transition-colors duration-300 transform hover:scale-105"
              >
                Send Message
              </button>
            </form>
          </div>
        </section>
      </main>

      {/* Footer - Sleek style */}
      <footer className="bg-gray-900 text-gray-400 py-6 text-center rounded-t-lg mt-8 border-t border-green-600 shadow-xl">
        <p>&copy; {new Date().getFullYear()} [Your Name]. All rights reserved.</p>
        <div className="flex justify-center space-x-4 mt-4">
          <a href="#" target="_blank" rel="noopener noreferrer" className="text-gray-400 hover:text-green-400 transition-colors duration-300">LinkedIn</a>
          <a href="#" target="_blank" rel="noopener noreferrer" className="text-gray-400 hover:text-green-400 transition-colors duration-300">GitHub</a>
          <a href="#" target="_blank" rel="noopener noreferrer" className="text-gray-400 hover:text-green-400 transition-colors duration-300">Twitter</a>
        </div>
      </footer>

      {/* Tailwind CSS for global styles and animations */}
      <script src="https://cdn.tailwindcss.com"></script>
      <style>
        {`
          @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
          body {
            font-family: 'Inter', sans-serif;
          }
          .font-inter {
            font-family: 'Inter', sans-serif;
          }

          /* Keyframe animations */
          @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
          }

          @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
          }

          @keyframes scaleIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
          }

          @keyframes fadeInLeft {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
          }

          @keyframes fadeInRight {
            from { opacity: 0; transform: translateX(50px); }
            to { opacity: 1; transform: translateX(0); }
          }

          /* Apply animations */
          .animate-fade-in {
            animation: fadeIn 1s ease-out forwards;
          }

          .animate-fade-in-up {
            animation: fadeInUp 0.8s ease-out forwards;
          }
          .animate-fade-in-up.delay-200 {
            animation-delay: 0.2s;
          }
          .animate-fade-in-up.delay-400 {
            animation-delay: 0.4s;
          }
          .animate-scale-in {
            animation: scaleIn 0.7s ease-out forwards;
          }
          .animate-fade-in-left {
            animation: fadeInLeft 0.8s ease-out forwards;
          }
          .animate-fade-in-right {
            animation: fadeInRight 0.8s ease-out forwards;
          }
        `}
      </style>
    </div>
  );
};

export default App;
