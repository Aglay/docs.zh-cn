---
title: "构造函数 (F#)"
description: "了解如何定义和使用 F # 中的构造函数来创建和初始化类和结构的对象。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e0da2250-29de-4145-a1be-e5faff080759
ms.openlocfilehash: 60ed93f1c1dc15e99465d969c9e4fd3e61c28ffa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="constructors"></a><span data-ttu-id="9eb91-104">构造函数</span><span class="sxs-lookup"><span data-stu-id="9eb91-104">Constructors</span></span>

<span data-ttu-id="9eb91-105">本主题介绍如何定义和使用构造函数来创建和初始化类和结构的对象。</span><span class="sxs-lookup"><span data-stu-id="9eb91-105">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>


## <a name="construction-of-class-objects"></a><span data-ttu-id="9eb91-106">类对象的构造</span><span class="sxs-lookup"><span data-stu-id="9eb91-106">Construction of Class Objects</span></span>
<span data-ttu-id="9eb91-107">类类型的对象具有构造函数。</span><span class="sxs-lookup"><span data-stu-id="9eb91-107">Objects of class types have constructors.</span></span> <span data-ttu-id="9eb91-108">有两种类型的构造函数。</span><span class="sxs-lookup"><span data-stu-id="9eb91-108">There are two kinds of constructors.</span></span> <span data-ttu-id="9eb91-109">其中一个是主构造函数，其参数之后的类型名称出现在括号内。</span><span class="sxs-lookup"><span data-stu-id="9eb91-109">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="9eb91-110">使用指定另一个可选的其他构造函数`new`关键字。</span><span class="sxs-lookup"><span data-stu-id="9eb91-110">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="9eb91-111">任何此类其他构造函数必须调用主构造函数。</span><span class="sxs-lookup"><span data-stu-id="9eb91-111">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="9eb91-112">主构造函数包含`let`和`do`出现在类定义开头的绑定。</span><span class="sxs-lookup"><span data-stu-id="9eb91-112">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="9eb91-113">A`let`绑定声明私有字段和类; 方法`do`绑定执行代码。</span><span class="sxs-lookup"><span data-stu-id="9eb91-113">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="9eb91-114">有关详细信息`let`绑定中类的构造函数，请参阅[`let`类中的绑定](let-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb91-114">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="9eb91-115">有关详细信息`do`绑定在构造函数，请参阅[`do`类中的绑定](do-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb91-115">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="9eb91-116">无论你想要调用的构造函数是具有主构造函数或其他构造函数，你可以通过创建对象`new`表达式，或不带可选`new`关键字。</span><span class="sxs-lookup"><span data-stu-id="9eb91-116">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="9eb91-117">你初始化对象构造函数自变量，通过列出自变量的顺序以及用逗号分隔并括在括号内，或在括号中使用命名自变量和值。</span><span class="sxs-lookup"><span data-stu-id="9eb91-117">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="9eb91-118">你还可以设置属性的对象的对象的构造过程使用的属性名称和分配值，就像使用名为构造函数自变量。</span><span class="sxs-lookup"><span data-stu-id="9eb91-118">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="9eb91-119">下面的代码演示具有一个构造函数和创建对象的各种方法的类。</span><span class="sxs-lookup"><span data-stu-id="9eb91-119">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="9eb91-120">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="9eb91-120">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="9eb91-121">构造的结构</span><span class="sxs-lookup"><span data-stu-id="9eb91-121">Construction of Structures</span></span>
<span data-ttu-id="9eb91-122">结构遵循类的所有的规则。</span><span class="sxs-lookup"><span data-stu-id="9eb91-122">Structures follow all the rules of classes.</span></span> <span data-ttu-id="9eb91-123">因此，你可以具有主构造函数，并可以使用来提供其他构造函数`new`。</span><span class="sxs-lookup"><span data-stu-id="9eb91-123">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="9eb91-124">但是，没有结构和类的一个重要区别： 结构可以具有默认构造函数 （即，一个不带任何参数），即使定义没有主构造函数。</span><span class="sxs-lookup"><span data-stu-id="9eb91-124">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="9eb91-125">默认构造函数初始化为该类型，通常是零或它的等效项的默认值的所有字段。</span><span class="sxs-lookup"><span data-stu-id="9eb91-125">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="9eb91-126">为结构定义任何构造函数必须具有至少一个参数，以便它们不与默认构造函数冲突。</span><span class="sxs-lookup"><span data-stu-id="9eb91-126">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="9eb91-127">此外，结构通常具有通过使用创建的字段`val`关键字; 类也有这些字段。</span><span class="sxs-lookup"><span data-stu-id="9eb91-127">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="9eb91-128">结构和具有通过使用定义的字段的类`val`关键字可以还在中初始化其他构造函数通过使用记录的表达式，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="9eb91-128">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="9eb91-129">有关详细信息，请参阅[显式字段：`val`关键字](explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb91-129">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>


## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="9eb91-130">在构造函数中执行的副作用</span><span class="sxs-lookup"><span data-stu-id="9eb91-130">Executing Side Effects in Constructors</span></span>
<span data-ttu-id="9eb91-131">类中的具有主构造函数可以执行中的代码`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="9eb91-131">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="9eb91-132">但是，如果你需要在其他构造函数，而不执行代码`do`绑定？</span><span class="sxs-lookup"><span data-stu-id="9eb91-132">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="9eb91-133">若要执行此操作，请使用`then`关键字。</span><span class="sxs-lookup"><span data-stu-id="9eb91-133">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="9eb91-134">仍执行主构造函数的副作用。</span><span class="sxs-lookup"><span data-stu-id="9eb91-134">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="9eb91-135">因此，输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="9eb91-135">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="9eb91-136">在构造函数中的自我标识符</span><span class="sxs-lookup"><span data-stu-id="9eb91-136">Self Identifiers in Constructors</span></span>
<span data-ttu-id="9eb91-137">其他成员，可以提供每个成员的定义中的当前对象的名称。</span><span class="sxs-lookup"><span data-stu-id="9eb91-137">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="9eb91-138">你还可将自我标识符置于类定义的第一行使用`as`紧跟构造函数参数的关键字。</span><span class="sxs-lookup"><span data-stu-id="9eb91-138">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="9eb91-139">下面的示例阐释了此语法。</span><span class="sxs-lookup"><span data-stu-id="9eb91-139">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="9eb91-140">在其他构造函数，你还可以定义自我标识符置于`as`后构造函数参数的子句。</span><span class="sxs-lookup"><span data-stu-id="9eb91-140">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="9eb91-141">下面的示例阐释了此语法。</span><span class="sxs-lookup"><span data-stu-id="9eb91-141">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="9eb91-142">当你尝试使用的对象，它已完全定义之前，会发生问题。</span><span class="sxs-lookup"><span data-stu-id="9eb91-142">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="9eb91-143">因此，自我标识符的使用可能导致编译器发出警告并插入其他检查，以确保之前初始化了对象，不会访问对象的成员。</span><span class="sxs-lookup"><span data-stu-id="9eb91-143">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="9eb91-144">你只应使用中的自我标识符`do`绑定主构造函数，或后`then`在其他构造函数中的关键字。</span><span class="sxs-lookup"><span data-stu-id="9eb91-144">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="9eb91-145">自我标识符的名称不一定要`this`。</span><span class="sxs-lookup"><span data-stu-id="9eb91-145">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="9eb91-146">它可以是任何有效的标识符。</span><span class="sxs-lookup"><span data-stu-id="9eb91-146">It can be any valid identifier.</span></span>


## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="9eb91-147">将值分配给在初始化属性</span><span class="sxs-lookup"><span data-stu-id="9eb91-147">Assigning Values to Properties at Initialization</span></span>
<span data-ttu-id="9eb91-148">你也可以通过追加形式的赋值的列表中的初始化代码的类对象的属性分配值`property = value`到一个构造函数的自变量列表。</span><span class="sxs-lookup"><span data-stu-id="9eb91-148">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="9eb91-149">下面的代码示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="9eb91-149">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="9eb91-150">以下版本的前面的代码演示普通自变量，可选自变量和一个构造函数调用中的属性设置的组合。</span><span class="sxs-lookup"><span data-stu-id="9eb91-150">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a><span data-ttu-id="9eb91-151">中继承的类的构造函数</span><span class="sxs-lookup"><span data-stu-id="9eb91-151">Constructors in inherited class</span></span>
<span data-ttu-id="9eb91-152">从具有构造函数的基类继承时, 你必须在继承子句中指定其自变量。</span><span class="sxs-lookup"><span data-stu-id="9eb91-152">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="9eb91-153">有关详细信息，请参阅[构造函数和继承](../inheritance.md#constructors-and-inheritance)。</span><span class="sxs-lookup"><span data-stu-id="9eb91-153">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="9eb91-154">静态构造函数或类型构造函数</span><span class="sxs-lookup"><span data-stu-id="9eb91-154">Static Constructors or Type Constructors</span></span>
<span data-ttu-id="9eb91-155">除了指定用于创建对象，静态代码`let`和`do`绑定可以编写在执行之前类型首次用于执行初始化类型级别的类类型。</span><span class="sxs-lookup"><span data-stu-id="9eb91-155">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="9eb91-156">有关详细信息，请参阅[`let`类中的绑定](let-bindings-in-classes.md)和[`do`类中的绑定](do-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb91-156">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9eb91-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9eb91-157">See Also</span></span>
[<span data-ttu-id="9eb91-158">成员</span><span class="sxs-lookup"><span data-stu-id="9eb91-158">Members</span></span>](index.md)