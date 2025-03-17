---
title: Tailwinnnnnd
deprecated: false
hidden: false
metadata:
  robots: index
---
<HTMLBlock>{`
<div className="flex justify-center items-center min-h-screen bg-gradient-to-br from-gray-100 to-gray-300 p-6">
      <div className="bg-white rounded-2xl p-8 m-6 max-w-xl shadow-2xl border border-gray-200 transform transition-all duration-300 hover:scale-105 hover:shadow-3xl">
        <h2 className="text-2xl font-extrabold text-gray-800 mb-6 flex items-center gap-2">
          <i className="fa-solid fa-rocket text-blue-500 animate-bounce" />
          {header}
        </h2>
        <div className="space-y-4 text-gray-700 text-lg">
          <p className="flex items-center gap-3">
            <i className="fa-solid fa-code text-indigo-500 text-xl" />
            Write{" "}
            <a
              href="https://docs.readme.com/main/v3.0/docs/building-custom-mdx-components"
              target="_blank"
              className="bg-blue-600 text-white px-4 py-2 rounded-full font-semibold shadow-md transition-all duration-300 hover:bg-blue-700 hover:shadow-lg active:scale-95"
            >
              MDX
            </a>{" "}
            to render interactive content.
          </p>
          <p className="flex items-center gap-3">
            <i className="fa-solid fa-pen text-green-500 text-xl" />
            Style elements with{" "}
            <a
              href="https://tailwindcss.com"
              target="_blank"
              className="bg-green-600 text-white px-4 py-2 rounded-full font-semibold shadow-md transition-all duration-300 hover:bg-green-700 hover:shadow-lg active:scale-95"
            >
              Tailwind CSS
            </a>.
          </p>
          <p className="flex items-center gap-3">
            <i className="fa-solid fa-lightbulb text-yellow-500 text-xl animate-pulse" />
            Need inspiration? Check out our{" "}
            <a
              href="https://github.com/readmeio/marketplace"
              target="_blank"
              className="bg-yellow-500 text-white px-4 py-2 rounded-full font-semibold shadow-md transition-all duration-300 hover:bg-yellow-600 hover:shadow-lg active:scale-95"
            >
              Marketplace
            </a>!
          </p>
        </div>
      </div>
    </div>
`}</HTMLBlock>