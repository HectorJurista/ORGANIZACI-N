# ORGANIZACIÓN
ANALIZA LA LEY DE VICTIMAS A TRAVES DE EROTHATOLOGIA  
import React, { useState } from 'react';

export default function ErothanatologyApp() {
  const [articleText, setArticleText] = useState<string>('');
  const [luciferResponse, setLuciferResponse] = useState<string>('');
  const [loading, setLoading] = useState<boolean>(false);

  const handleInputChange = (event: React.ChangeEvent<HTMLTextAreaElement>) => {
    setArticleText(event.target.value);
  };

  const handleAnalyzeClick = async () => {
    setLoading(true);
    // Simulate an API call to the "Lucifer" chatbot
    // Replace this with your actual API endpoint and logic
    try {
      await new Promise((resolve) => setTimeout(resolve, 1500)); // Simulate delay
      const response = await analyzeArticle(articleText);
      setLuciferResponse(response);
    } catch (error) {
      setLuciferResponse("An error occurred while analyzing the article.");
    } finally {
      setLoading(false);
    }
  };

  // Placeholder function for analyzing the article
  const analyzeArticle = async (article: string): Promise<string> => {
    // This is a placeholder - replace with actual logic
    // that uses the Erothanatology principles
    // based on neurosciences, philosophy, and law.

    const keywords = ["reparación simbólica", "resiliencia", "conflicto", "reconciliación"];
    let analysis = "Lucifer's Analysis:\n\n";

    if (article.toLowerCase().includes(keywords[0])) {
      analysis += "The article references the importance of symbolic reparation for victims, indicating a need to address the intangible wounds of war and conflict through recognition, memorialization, and restorative justice.\n\n";
    }

    if (article.toLowerCase().includes(keywords[1])) {
      analysis += "The concept of resiliencia is central to the article, highlighting the capacity of individuals and communities to overcome adversity and rebuild their lives after experiencing trauma and loss. Fostering resiliencia requires providing psychosocial support, promoting social cohesion, and empowering victims to become agents of their own recovery.\n\n";
    }

    if (article.toLowerCase().includes(keywords[2])) {
      analysis += "The article underscores the role of conflicto in shaping the experiences of victims, acknowledging the complex dynamics of power, violence, and displacement that contribute to their suffering. Understanding the root causes of conflicto is essential for preventing future atrocities and building lasting peace.\n\n";
    }

    if (article.toLowerCase().includes(keywords[3])) {
      analysis += "The article emphasizes the importance of reconciliación as a means of healing divisions and fostering social harmony after periods of conflict. Reconciliación requires acknowledging past wrongs, promoting dialogue and understanding, and creating opportunities for victims and perpetrators to engage in meaningful interactions.\n\n";
    }

    if (!article.toLowerCase().includes(keywords[0]) && !article.toLowerCase().includes(keywords[1]) && !article.toLowerCase().includes(keywords[2]) && !article.toLowerCase().includes(keywords[3])) {
      analysis += "The analysis of the provided text did not yield any of the key words related to the Erothanatology principles: reparación simbólica, resiliencia, conflicto, or reconciliación. Please provide a text that contains one of these keywords to extract the desired meaning";
    }
    return analysis;
  };

  return (
    <div className="bg-gray-50 min-h-screen flex items-center justify-center py-12 px-4 sm:px-6 lg:px-8">
      <div className="max-w-3xl w-full space-y-8 bg-white rounded-xl shadow-lg p-8">
        <div>
          <h2 className="mt-6 text-center text-3xl font-extrabold text-gray-900">
            Erothanatology Analysis
          </h2>
          <p className="mt-2 text-center text-sm text-gray-600">
            Enter an article from the Victims' Law to analyze its Erothanatological implications.
          </p>
        </div>

        <div className="space-y-4">
          <div>
            <label htmlFor="article" className="block text-sm font-medium text-gray-700">
              Article Text
            </label>
            <div className="mt-1">
              <textarea
                id="article"
                name="article"
                rows={4}
                className="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md"
                placeholder="Enter the article text here..."
                value={articleText}
                onChange={handleInputChange}
              />
            </div>
          </div>

          <div>
            <button
              onClick={handleAnalyzeClick}
              disabled={loading}
              className={`w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white ${
                loading
                  ? 'bg-gray-400 cursor-not-allowed'
                  : 'bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500'
              }`}
            >
              {loading ? 'Analyzing...' : 'Analyze with Lucifer'}
            </button>
          </div>

          {luciferResponse && (
            <div>
              <label htmlFor="response" className="block text-sm font-medium text-gray-700">
                Lucifer's Interpretation
              </label>
              <div className="mt-1">
                <textarea
                  id="response"
                  name="response"
                  rows={6}
                  className="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md"
                  value={luciferResponse}
                  readOnly
                />
              </div>
            </div>
          )}
        </div>
      </div>
    </div>
  );
}
